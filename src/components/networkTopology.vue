<template>
	<div class="networkTopology" :style="{height: myCanvasHeight}">
		<div>
			<div id="jrjd">
				{{treeData.name}}
			</div>
		</div>
		
		<div id="hjjd_outer_id">
			<div><canvas id="line" class="canvasDiv"></canvas></div>
			<div class="hjjd" v-for="(hjjdItem, hjjdIndex) in treeData.children" :key="hjjdIndex" :id="'hjjd_'+hjjdIndex" @click="clickHjjd(hjjdItem, hjjdIndex)">
				<div :class="{'hjjd_item':(hjjdIndex != nowCheckedHjjd_index),'hjjd_item_checked':(hjjdIndex == nowCheckedHjjd_index)}">
					<div :class="{'hjjd_name':true,'hjjd_checked':(hjjdIndex == nowCheckedHjjd_index)}">
						{{hjjdItem.name}}
					</div>
					<div  v-for="(item, index) in hjjdItem.sensorTypeCountList" :key="index">
						<div class="sensorType">
							<span :style="{'color':sensorTypeColorChoose(item.sensorType),'padding':'0 3px'}">
								[
								<div :style="{'backgroundColor':sensorTypeColorChoose(item.sensorType),'display':'inline-block','width':'12px','height':'8px'}" style=""></div>	
								]
							</span>
							<span class="sensorTypeName">{{item.sensorType}}</span>
							<span style="color:rgb(0,255,246);margin-left:6px;">{{item.count}}</span>
						</div>
					</div>
					<div class="warningOffline" style="margin-left:30px;font-size:12px;">
						<!-- <div :style="{width:'34px',height:'34px',backgroundColor:'#3c2e2f',borderRadius:'50%', marginRight: '20px'}" @click.stop="clickHjjd_Warning(hjjdItem)">
							<i style="color:red;font-size: 10px;margin-top: 5px;" class="fa fa-exclamation-triangle"></i>
							<div>{{hjjdItem.errorCount}}</div>
						</div> -->
						<div :style="{width:'34px',height:'34px',backgroundColor:'#243232',borderRadius:'50%'}" @click.stop="clickHjjd_Offline(hjjdItem, hjjdIndex)">
							<i style="color:#e2514f;font-size: 10px;margin-top: 5px;" class="fa fa-chain-broken"></i>
							<div style="margin-top: -3px;">{{hjjdItem.offlineCount}}</div>
						</div>
					</div>
				</div>
			</div>
		</div>
        <transition name="el-zoom-in-bottom">
            <div v-show="drawer" class="drawer_outer">
                <div class="drawer_btn">
                    <i style="font-size: 26px;float:right;" class="fa fa-window-close" @click="closeDrawer"></i>
                </div>
                <div style="max-height: 600px; overflow: auto;">
                    <canvas id="sensorListDetail" ></canvas>
                </div>
            </div>
        </transition>
	</div>
</template>
<script>
import _ from 'lodash'
export default {
    name:'meshedNetwork',
    props:{
        // 数据源
        treeData:{
            type: Object,
            required: true,
        },
        // 传感器名称对应颜色标记（传感器名称：颜色）;其中default为没有配置色系的其他传感器类型默认色
        sensorTypeColors:{
            type: Object,
            default:{
                'default':'#ffffff'
            }
        } 
    },
    data(){
        return {
            // 当前选中汇聚节点
            nowCheckedHjjd_index: -1,
            // 点击详情模态框显示标志位
            drawer: false,
            // 模态框详情动画标志位：false收回，true展开
            drawer_animation: false,
            // 汇聚节点下传感器信息
			sensorList: [],
			myCanvasHeight: '100%'
        }
    },
    watch:{
        treeData(val, oldVal){
            // DOM渲染结束再执行
            this.$nextTick(function () {
                this.drawLine()
            })
        }
	},
	computed:{
        /**
         * 图表resize节流，这里使用了lodash，也可以自己使用setTimout实现节流
         */
        meshedNetworkChartResize() {
            return _.throttle(() => this.drawLine(), 300)
        }
    },
    mounted() { 
        window.addEventListener('resize', this.meshedNetworkChartResize)
    },
    destroyed() {
        window.removeEventListener('resize', this.meshedNetworkChartResize)
    },
    methods:{
        // 选择传感器颜色(没有匹配到时显示default颜色)
        sensorTypeColorChoose(sensorType = 'default'){
            return this.sensorTypeColors[sensorType] || this.sensorTypeColors['default']
        },
        // 绘制左侧发射线
        drawLine(canvasWidth = 200){
			let canvas = document.getElementById('line')
			let jrjdDiv = document.getElementById('jrjd')
			let hjjdDiv = document.getElementById('hjjd_outer_id') 
			canvas.width = canvasWidth
			this.myCanvasHeight = this.canvasHeight(hjjdDiv, this.treeData.children)
            canvas.height = this.myCanvasHeight
            
			let ctx = canvas.getContext('2d');
			let jrjdDiv_height = jrjdDiv.offsetHeight  // 接入节点高度+border
			
			// 发射线原点，接入节点发射
			let X0 = 0.5
			let Y0 = jrjdDiv.offsetTop + jrjdDiv_height/2

			ctx.strokeStyle = '#00ffff';    // 00ffff
			ctx.lineWidth = 1;
			for(let item in this.treeData.children){
				let index = item*1 + 1    // item从0开始
				let tailCoordinate = this.lineTailCoordinate(hjjdDiv, canvas.width, index)
				let item_x = tailCoordinate.x    // 所有发射线终点x轴都相等
				let item_y = tailCoordinate.y   // 计算每个发射线终点y轴
				// 发射线(现在是直线，后期可以考虑贝塞尔曲线尝试)
				ctx.moveTo(X0, Y0);
				ctx.lineTo(item_x, item_y);
				ctx.stroke();
				// 圆点
				ctx.beginPath();
				ctx.fillStyle = '#00ffff';
				ctx.arc(item_x, item_y,5,0,2*Math.PI,false)
				ctx.closePath()
				ctx.shadowColor = "#00ffff";   // 发光效果
				ctx.shadowBlur = 10;      
				ctx.fill();  // "填充"当前绘图
				// 箭头线
				ctx.shadowColor = "rgba(0,0,0,0)";   // 去除发光效果
				ctx.moveTo(item_x, item_y);
				ctx.lineTo(item_x + 20, item_y + 16);
				ctx.moveTo(item_x, item_y);
				ctx.lineTo(item_x + 20, item_y - 16);
				ctx.stroke();
			}
		},
		// 左侧发射线canvas高度计算
		canvasHeight(hjjdDiv, hjjdArr){
			let hjjdDiv_child1 = hjjdDiv.children[1]    // 汇聚节点统计横条
			let hjjd_marginTop = hjjdDiv_child1.offsetTop   // 汇聚节点上方偏移量
			let hjjdDiv_height = hjjdDiv_child1.clientHeight   // 汇聚节点高度
			return hjjdArr.length * (hjjdDiv_height + hjjd_marginTop);
		},
		// 发射线尾部坐标计算
		lineTailCoordinate(hjjdDiv, canvasWidth,index){
			let dot_offsetX = 16    // 圆点向左偏移位移（为了让出圆点和划两条发散线段的距离）
			let hjjdDiv_child1 = hjjdDiv.children[1]    // 0为canvas的div，1开始为统计横条
			let hjjd_marginTop = hjjdDiv_child1.offsetTop  // 汇聚节点上方偏移量
			let hjjdDiv_height = hjjdDiv_child1.clientHeight   // 汇聚节点高度
			return {
				x: canvasWidth - dot_offsetX,
				y: hjjd_marginTop * index + hjjdDiv_height*(index - 0.5)
			}
		},
        // 打开传感器详情模态
        openDrawer(hjjdIndex){
            // 同一个item就点击切换详情页开关
            if(this.nowCheckedHjjd_index === hjjdIndex){
                this.drawer = !this.drawer
                if(this.drawer){
                    this.drawSensorListDrawer('sensorListDetail',this.sensorList)
                }
            }else{    // 不是同一个item就打开
                this.nowCheckedHjjd_index = hjjdIndex
                this.drawer = false
                setTimeout(() => {
                    this.drawer = true
                    this.drawSensorListDrawer('sensorListDetail',this.sensorList)
                },100)
            }
        },
        // 绘制传感器详情弹框
		drawSensorListDrawer(canvasId, sensorList){
			let canvas = document.getElementById(canvasId)
			let canvas_padding = 30   // canvas  padding
			let root_line_length = 40   // 左边根线条长度
			let child_line_length = 20   // 子节点树枝长度
			let font_size = 16    // 传感器列表字体
			let row_gap = 10       // 行间距
			let item_width  = 400   // 每个传感器宽度
			let column_gap = 80    // 列间隙
			let item_height = font_size + 4   // 每行高度（字所占高度是大于它自身高度的，行高比字高10）
			let bottom_height = item_height + 10  // 根节点的底部高度（比项高20）
			let root_r = 5    // 根节点圆点半径
			let child_r = 3    // 节点圆点半径

			// 计算sensorList的宽度和高度(每行三个)
			let num_every_row = 2      // 每行个数
			let total_height = Math.ceil(sensorList.length/num_every_row) * (item_height+row_gap) + canvas_padding * 2 + bottom_height
			let total_width = (item_width+column_gap) * num_every_row + canvas_padding * 2 + child_line_length + root_line_length
			
			canvas.height = total_height; 
			canvas.width= total_width;
			let ctx = canvas.getContext('2d');
			ctx.fillStyle = '#0a3634'                     
			ctx.fillRect(0, 0,total_width, total_height);   // 绘制背景色
			
            ctx.lineWidth = 1;
            // 无传感器信息则返回
			if(sensorList.length <= 0){
                ctx.font = font_size + "px 黑体";
				ctx.fillStyle = '#e2514f';
				ctx.fillText('无传感器信息',root_line_length+canvas_padding, canvas_padding + bottom_height/2, item_width);
                return 
			}
			// 根节点圆点
			ctx.beginPath();
			ctx.strokeStyle = '#00ffff';    // 00ffff
			ctx.fillStyle = '#00ffff';
			ctx.arc(canvas_padding, total_height - canvas_padding, root_r ,0,2*Math.PI,false)
			ctx.closePath()
			ctx.shadowColor = "#00ffff";   // 发光效果
			ctx.shadowBlur = 10;      
			ctx.fill();  // "填充"当前绘图
			ctx.closePath();

			// 根节点线
			ctx.shadowColor = "rgba(0,0,0,0)";   // 去除发光效果
			ctx.strokeStyle = '#428581';    // 00ffff
			ctx.beginPath();
			ctx.moveTo(canvas_padding + root_r, total_height - canvas_padding);
			// 横线
			ctx.lineTo(root_line_length + canvas_padding, total_height - canvas_padding);  
			// 竖线
			ctx.lineTo(root_line_length + canvas_padding, item_height/2 + canvas_padding); 
			ctx.stroke();
			ctx.closePath();
			let column_count = (sensorList.length < num_every_row) ? sensorList.length: num_every_row    // 共几列
			for(let i = 0; i < column_count - 1;i++){
				ctx.beginPath();
				ctx.moveTo(root_line_length + canvas_padding + (item_width + column_gap) * i, total_height - canvas_padding);
				ctx.lineTo(root_line_length + canvas_padding + (item_width + column_gap)*(i+1), total_height - canvas_padding);     // 横线
				ctx.lineTo(root_line_length + canvas_padding + (item_width + column_gap)*(i+1), item_height/2 + canvas_padding);                    // 竖线
				ctx.stroke();
				ctx.closePath();
			}

			for(let index in sensorList){
				let column_num = index*1% num_every_row + 1           // 第几列
				let row_num = parseInt(index*1/num_every_row) + 1    // 第几行
				let column_x = 0                         // x轴坐标
				let yItem = 0                            // y轴坐标
				yItem = item_height/2 + (item_height+row_gap) * (row_num - 1) + canvas_padding
				column_x = root_line_length + canvas_padding + (item_width + column_gap)*(column_num - 1)    // 这一列的横坐标
				
				ctx.beginPath()
				ctx.strokeStyle = '#428581';    // 00ffff
				ctx.moveTo(column_x,yItem);
				ctx.lineTo(column_x+child_line_length, yItem); 
				ctx.stroke();
				ctx.closePath();
				
				// 圆点
				ctx.beginPath();
				let color = sensorList[index].online ? '#00ffff' : '#e2514f'   // 线条颜色
				let font_color = sensorList[index].online ? 'white' : '#e2514f'   // 线条颜色
				ctx.strokeStyle = color
				ctx.fillStyle = color;
				ctx.arc(column_x+child_line_length, yItem, child_r,0,2*Math.PI,false)
				ctx.closePath()
				ctx.shadowColor = color;   // 发光效果
				ctx.shadowBlur = 10;      
				ctx.fill();  // "填充"当前绘图
				ctx.closePath();
				// 传感器名称打印
				ctx.shadowColor = "rgba(0,0,0,0)";   // 去除发光效果
				ctx.font = font_size + "px 黑体";
				ctx.fillStyle = font_color;
				ctx.fillText(sensorList[index].name,column_x+child_line_length + 5, yItem + font_size/2, item_width);
			}	
        },
        // 点击汇聚节点
        clickHjjd(hjjdItem, hjjdIndex){
			this.sensorList = hjjdItem.children
			this.openDrawer(hjjdIndex)
        },
        // 关闭传感器详情弹框
		closeDrawer(){
			this.drawer = false
			this.nowCheckedHjjd_index = -1
			this.sensorList = []
        },
        // 点击离线数量
		clickHjjd_Offline(hjjdItem, hjjdIndex){
			this.sensorList = hjjdItem.children.filter((i) => { return i.online == 0})
			this.openDrawer(hjjdIndex)
        },
        // 点击告警数量（暂留）
        clickHjjd_Warning(hjjdItem){},
    }
}
</script>
<style>

</style>

<style scoped>
.networkTopology {
    /* height:100%; */
    width:100%;
	color: white;
	display: flex;
	flex-direction:row;
	justify-content:flex-start;
	align-items:center;
	overflow: auto;
}
#jrjd {
	background-color: rgba(66,133,129,1);
	border: 10px solid rgba(21,82,80,.28);
	border-radius: 50%;
	width: 100px;
	height: 100px;
	min-width: 100px;
	min-height: 100px;
	line-height: 100px;
	font-size: 18px;
	text-align: center;
}
.canvasDiv{
	float: left;
}
.hjjd {
	font-size: 14px;
	margin-top: 20px;
	display: flex;
	flex-direction: column;
	justify-content: flex-start;
	flex: auto;
	text-align: center;
	white-space: nowrap;   /* 强制不换行 */
	height: 54px;
}
#hjjd_outer_id{
	height: 100%;
}

.hjjd_item {
	background: linear-gradient(to right,rgba(26,78,75,1) 0%,rgba(26,78,75,0.5)50%,rgba(26,78,75,0.3) 80%, rgba(26,78,75,0) 100%); 
	border-top-left-radius: 35px;
	border-bottom-left-radius: 35px;
	padding: 10px;
	display: flex;
	flex-direction:row;
	justify-content:flex-start;
	align-items:center;
	cursor: pointer;
	height: 54px;
}
.hjjd_item:hover {
	background: linear-gradient(to right,rgba(7,45,43,1) 0%,rgba(7,45,43,0.5)50%,rgba(7,45,43,0.3) 80%, rgba(7,45,43,0) 100%);
	color: #ffcc50;
}
.hjjd_item_checked {
	border-top-left-radius: 35px;
	border-bottom-left-radius: 35px;
	padding: 10px;
	display: flex;
	flex-direction:row;
	justify-content:flex-start;
	align-items:center;
	cursor: pointer;
	background: linear-gradient(to right,rgba(7,45,43,1) 0%,rgba(7,45,43,0.5)50%,rgba(7,45,43,0.3) 80%, rgba(7,45,43,0) 100%); 
	color: #ffcc50;
}
.hjjd_name {
	border: 1px solid rgb(0,255,255);
	width: 100px;
	min-width: 100px;
	padding: 6px;
	overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
}
.hjjd_name:hover {
	box-shadow: rgb(0, 255, 247) 0px 0px 20px;
}
.hjjd_checked {
	box-shadow: rgb(0, 255, 247) 0px 0px 20px;
}
.sensorType {
	margin: 0 20px;
}
.warningOffline {
	display: flex;
	flex-direction:row;
	justify-content:flex-start;
	align-items:center;
}
#drawer_close_btn {
	position:absolute;
	right: 0;
}
#drawer_close_btn:hover {
	color:#ffcc50;
}
.drawer_outer{
    position: fixed;
    left: 466px;
    top: 0;
    bottom: 0;
    display: flex;
	flex-direction:column;
	justify-content:center;
}

#drawer_sensorList{
	padding: 10px;
	border: 1px solid rgb(0,255,255);
	background-color: #0a3634;
	overflow-y: auto;
}
.drawer_sensorItem{
    /* border-left: solid 1px green;
    border-bottom: solid 1px green; */
}
.drawer_sensorItem:hover .drawer_sensorItem_name, drawer_sensorItem:hover .drawer_sensorItem_icon{
	color: #ffc600;
	cursor: pointer;
}
.drawer_sensorItem_icon{
	color:#a3a6a6;font-size: 10px;margin-top: 5px;
}
.drawer_btn {
	position: relative;
}
.drawer_btn:hover{
	color: #ffc600;
}
.sensorTypeName{
	display: inline-flex;
    max-width: 100px;
    white-space: nowrap;
    overflow: hidden;
}
</style>
