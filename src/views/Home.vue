<template>
	<div id="meshedNetwork">
        <networkTopology :sensorTypeColors = "sensorTypeColors" :treeData="treeData"></networkTopology>
	</div>
</template>
<script>
import networkTopology from '@/components/networkTopology.vue'
export default {
    name:'meshedNetwork',
    components:{
        networkTopology
    },
    data(){
        return {
            // 传感器名称对应颜色标记（传感器名称：颜色）;其中default为没有配置色系的其他传感器类型默认色
            sensorTypeColors:{
                "温度传感器":'#ea6948',
                "形变传感器":'#006e63',
                "温湿度传感器":'#cb9a8f',
                "水浸传感器":'#a3a380',
                'default':'#ffffff',
                // '局放传感器':'#f0d289',
                // 'xx传感器':'#69b3e6',
                // 'xx传感器':'#93d5ae',
            },
            // 数据源
            treeData:{}
		    }
    },
    mounted() { 
        this.queryMeshedNetwork()
    },
    methods:{
        // 选择传感器颜色(没有匹配到时显示default颜色)
        sensorTypeColorChoose(sensorType = 'default'){
            return this.sensorTypeColors[sensorType] || this.sensorTypeColors['default']
        },
        queryMeshedNetwork(){
			// 此处模拟请求后台接口获取数据
			setTimeout(() => {
				this.treeData = {
					"children": [
						{
						"children": [
								{
								"name": "A节点_温度传感器_TP20C01",
								"online": 1
								},
								{
								"name": "A节点_温度传感器_TP20C04",
								"online": 1
								},
								{
								"name": "A节点_温度传感器_TP20C05",
								"online": 1
								},
								{
								"name": "A节点_温度传感器_TP20C03",
								"online": 1
								},
								{
								"name": "A节点_温度传感器_TP20BFF",
								"online": 1
								},
								{
								"name": "A节点_温度传感器_TP20C0A",
								"online": 1
								},
								{
								"name": "10kVⅠ段母线压变1015手车_温度传感器_TP20C40",
								"online": 0
								},
								{
								"name": "10kVⅠ段母线压变1015手车_温湿度传感器_IRQ98968A",
								"online": 1
								},
								{
								"name": "2号接地变_温湿度传感器_IRQ98969D",
								"online": 1
								},
								{
								"name": "1号主变10kV侧101开关柜体_温湿度传感器_IRQ989682",
								"online": 1
								},
								{
								"name": "1号主变10kV侧101开关柜体_温度传感器_TP20BD5",
								"online": 1
								},
								{
								"name": "1号主变10kV侧101开关柜体_温度传感器_TP20BD6",
								"online": 1
								},
								{
								"name": "1号主变10kV侧101开关柜体_温度传感器_TP20BD7",
								"online": 1
								},
								{
								"name": "1号主变10kV侧101开关柜体_温度传感器_TP20BD8",
								"online": 1
								},
								{
								"name": "1号主变10kV侧101开关柜体_温度传感器_TP20BD9",
								"online": 1
								},
								{
								"name": "1号主变10kV侧101开关柜体_温度传感器_TP20BDA",
								"online": 1
								},
								{
								"name": "10kV志达111开关柜体_温湿度传感器_IRQ98968F",
								"online": 1
								},
								{
								"name": "10kV志达111开关柜体_温度传感器_TP20BEA",
								"online": 1
								},
								{
								"name": "10kV志达111开关柜体_温度传感器_TP20BEB",
								"online": 1
								},
								{
								"name": "10kV志达111开关柜体_温度传感器_TP20BEF",
								"online": 1
								},
								{
								"name": "10kV志达111开关柜体_温度传感器_TP20BF2",
								"online": 1
								},
								{
								"name": "10kV志达111开关柜体_温度传感器_TP20BF4",
								"online": 1
								},
								{
								"name": "10kV志达111开关柜体_温度传感器_TP20BF5",
								"online": 1
								},
								{
								"name": "10kV兴越112开关柜体_温湿度传感器_IRQ989689",
								"online": 1
								},
								{
								"name": "10kV兴越112开关柜体_温度传感器_TP20C09",
								"online": 0
								},
								{
								"name": "10kV兴越112开关柜体_温度传感器_TP20C0B",
								"online": 0
								},
								{
								"name": "10kV兴越112开关柜体_温度传感器_TP20BED",
								"online": 0
								},
								{
								"name": "10kV兴越112开关柜体_温度传感器_TP20BE5",
								"online": 0
								},
								{
								"name": "10kV兴越112开关柜体_温度传感器_TP20BF8",
								"online": 0
								},
								{
								"name": "10kV兴越112开关柜体_温度传感器_TP20BE9",
								"online": 0
								},
								{
								"name": "10kV高铁113开关柜体_温湿度传感器_IRQ98968B",
								"online": 1
								},
								{
								"name": "10kV高铁113开关柜体_温度传感器_TP20BF9",
								"online": 1
								},
								{
								"name": "10kV高铁113开关柜体_温度传感器_TP20BFA",
								"online": 1
								},
								{
								"name": "10kV高铁113开关柜体_温度传感器_TP20BFB",
								"online": 1
								},
								{
								"name": "10kV高铁113开关柜体_温度传感器_TP20BFC",
								"online": 1
								},
								{
								"name": "10kV高铁113开关柜体_温度传感器_TP20BFD",
								"online": 1
								},
								{
								"name": "10kV高铁113开关柜体_温度传感器_TP20BFE",
								"online": 1
								},
								{
								"name": "10kV禾邦114开关柜体_温湿度传感器_IRQ98968C",
								"online": 1
								},
								{
								"name": "10kV禾邦114开关柜体_温度传感器_TP20BE4",
								"online": 1
								},
								{
								"name": "10kV禾邦114开关柜体_温度传感器_TP20C2F",
								"online": 1
								},
								{
								"name": "10kV禾邦114开关柜体_温度传感器_TP20C31",
								"online": 1
								},
								{
								"name": "10kV禾邦114开关柜体_温度传感器_TP20C30",
								"online": 1
								},
								{
								"name": "10kV禾邦114开关柜体_温度传感器_TP20C34",
								"online": 1
								},
								{
								"name": "10kV禾邦114开关柜体_温度传感器_TP20C37",
								"online": 1
								},
								{
								"name": "10kV东翔116开关柜体_温湿度传感器_IRQ98968E",
								"online": 1
								},
								{
								"name": "10kV东翔116开关柜体_温度传感器_TP20C06",
								"online": 1
								},
								{
								"name": "10kV东翔116开关柜体_温度传感器_TP20C07",
								"online": 1
								},
								{
								"name": "10kV东翔116开关柜体_温度传感器_TP20C08",
								"online": 1
								},
								{
								"name": "10kV东翔116开关柜体_温度传感器_TP20C19",
								"online": 1
								},
								{
								"name": "10kV东翔116开关柜体_温度传感器_TP20C1A",
								"online": 1
								},
								{
								"name": "10kV东翔116开关柜体_温度传感器_TP20C1C",
								"online": 1
								},
								{
								"name": "10kV1号电容器191开关柜体_温湿度传感器_IRQ989687",
								"online": 1
								},
								{
								"name": "10kV1号电容器191开关柜体_温度传感器_TP20C0C",
								"online": 0
								},
								{
								"name": "10kV1号电容器191开关柜体_温度传感器_TP20C0F",
								"online": 0
								},
								{
								"name": "10kV1号电容器191开关柜体_温度传感器_TP20C14",
								"online": 0
								},
								{
								"name": "10kV1号电容器191开关柜体_温度传感器_TP20C25",
								"online": 0
								},
								{
								"name": "10kV1号电容器191开关柜体_温度传感器_TP20C2E",
								"online": 0
								},
								{
								"name": "10kV1号电容器191开关柜体_温度传感器_TP20C2C",
								"online": 0
								},
								{
								"name": "1号接地变181开关柜体_温湿度传感器_IRQ989686",
								"online": 1
								},
								{
								"name": "1号接地变181开关柜体_温度传感器_TP20C0E",
								"online": 0
								},
								{
								"name": "1号接地变181开关柜体_温度传感器_TP20C15",
								"online": 0
								},
								{
								"name": "1号接地变181开关柜体_温度传感器_TP20C16",
								"online": 0
								},
								{
								"name": "1号接地变181开关柜体_温度传感器_TP20C1B",
								"online": 0
								},
								{
								"name": "1号接地变181开关柜体_温度传感器_TP20C1D",
								"online": 0
								},
								{
								"name": "1号接地变181开关柜体_温度传感器_TP20C22",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段110开关柜体_温湿度传感器_IRQ989681",
								"online": 1
								},
								{
								"name": "10kVⅠ、Ⅵ段分段110开关柜体_温度传感器_TP20C0D",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段110开关柜体_温度传感器_TP20C1E",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段110开关柜体_温度传感器_TP20C1F",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段110开关柜体_温度传感器_TP20C23",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段110开关柜体_温度传感器_TP20C24",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段110开关柜体_温度传感器_TP20C2D",
								"online": 0
								},
								{
								"name": "10kVⅠ段母线压变1015手车_温度传感器_TP20C33",
								"online": 0
								},
								{
								"name": "10kVⅠ段母线压变1015手车_温度传感器_TP20C3C",
								"online": 0
								},
								{
								"name": "温湿度传感器_IRQ9896D1",
								"online": 1
								},
								{
								"name": "A节点_温湿度传感器_IRQ98968D",
								"online": 1
								}
							],
							"sensorTypeCountList":[
								{
									sensorType: "温度传感器",
									count: 63
								},
								{
									sensorType: "温湿度传感器",
									count: 13
								}
							],
							"offlineCount": 27,
							"name": "1号汇聚节点",
							},
							{
							"children": [
								{
								"name": "10kVⅠ、Ⅵ段分段1101隔离手车柜体_温湿度传感器_IRQ989680",
								"online": 1
								},
								{
								"name": "10kVⅠ、Ⅵ段分段1101隔离手车柜体_温度传感器_TP20C26",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段1101隔离手车柜体_温度传感器_TP20C27",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段1101隔离手车柜体_温度传感器_TP20C28",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段1101隔离手车柜体_温度传感器_TP20C29",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段1101隔离手车柜体_温度传感器_TP20C2A",
								"online": 0
								},
								{
								"name": "10kVⅠ、Ⅵ段分段1101隔离手车柜体_温度传感器_TP20C2B",
								"online": 0
								},
								{
								"name": "10kV1号接地变_温湿度传感器_IRQ989684",
								"online": 1
								},
								{
								"name": "10kV仁发161开关柜体_温湿度传感器_IRQ9896C7",
								"online": 1
								},
								{
								"name": "10kV仁发161开关柜体_温度传感器_TP20CB5",
								"online": 1
								},
								{
								"name": "10kV仁发161开关柜体_温度传感器_TP20CB6",
								"online": 1
								},
								{
								"name": "10kV仁发161开关柜体_温度传感器_TP20CB7",
								"online": 1
								},
								{
								"name": "10kV仁发161开关柜体_温度传感器_TP20D85",
								"online": 0
								},
								{
								"name": "10kV仁发161开关柜体_温度传感器_TP20D86",
								"online": 1
								},
								{
								"name": "10kV仁发161开关柜体_温度传感器_TP20D87",
								"online": 1
								},
								{
								"name": "10kV仁发161开关柜体_温度传感器_TP20CB8",
								"online": 1
								},
								{
								"name": "10kV仁发161开关柜体_温度传感器_TP20CB9",
								"online": 1
								},
								{
								"name": "10kV仁发161开关柜体_温度传感器_TP20CBA",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温湿度传感器_IRQ9896C8",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温度传感器_TP20CBB",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温度传感器_TP20CBC",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温度传感器_TP20CBD",
								"online": 1
								},
								{
								"name": "10kV航天163开关柜体_温湿度传感器_IRQ9896C9",
								"online": 1
								},
								{
								"name": "10kV航天163开关柜体_温度传感器_TP20D1C",
								"online": 1
								},
								{
								"name": "10kV航天163开关柜体_温度传感器_TP20D1D",
								"online": 1
								},
								{
								"name": "10kV航天163开关柜体_温度传感器_TP20D1E",
								"online": 1
								},
								{
								"name": "10kV航天163开关柜体_温度传感器_TP20D79",
								"online": 1
								},
								{
								"name": "10kV航天163开关柜体_温度传感器_TP20D7A",
								"online": 0
								},
								{
								"name": "10kV航天163开关柜体_温度传感器_TP20D7B",
								"online": 1
								},
								{
								"name": "10kV蓝光165开关柜体_温湿度传感器_IRQ9896CB",
								"online": 1
								},
								{
								"name": "10kV蓝光165开关柜体_温度传感器_TP20D22",
								"online": 1
								},
								{
								"name": "10kV蓝光165开关柜体_温度传感器_TP20D23",
								"online": 1
								},
								{
								"name": "10kV蓝光165开关柜体_温度传感器_TP20D24",
								"online": 1
								},
								{
								"name": "10kV蓝光165开关柜体_温度传感器_TP20D2B",
								"online": 1
								},
								{
								"name": "10kV蓝光165开关柜体_温度传感器_TP20D2C",
								"online": 1
								},
								{
								"name": "10kV蓝光165开关柜体_温度传感器_TP20D2D",
								"online": 1
								},
								{
								"name": "10kV8号电容器198开关柜体_温湿度传感器_IRQ9896BD",
								"online": 1
								},
								{
								"name": "10kV8号电容器198开关柜体_温度传感器_TP20D3B",
								"online": 0
								},
								{
								"name": "10kV8号电容器198开关柜体_温度传感器_TP20D3C",
								"online": 0
								},
								{
								"name": "10kV8号电容器198开关柜体_温度传感器_TP20D3D",
								"online": 0
								},
								{
								"name": "10kV8号电容器198开关柜体_温度传感器_TP20D3E",
								"online": 0
								},
								{
								"name": "10kV8号电容器198开关柜体_温度传感器_TP20D3F",
								"online": 0
								},
								{
								"name": "10kV8号电容器198开关柜体_温度传感器_TP20D40",
								"online": 0
								},
								{
								"name": "温湿度传感器_IRQ9896D0",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温度传感器_TP20D8F",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温度传感器_TP20D90",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温度传感器_TP20D91",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温度传感器_TP20D19",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温度传感器_TP20D1A",
								"online": 1
								},
								{
								"name": "10kV春水162开关柜体_温度传感器_TP20D1B",
								"online": 1
								},
								{
								"name": "10kV超华164开关柜体_温湿度传感器_IRQ9896CA",
								"online": 1
								},
								{
								"name": "10kV超华164开关柜体_温度传感器_TP20D34",
								"online": 1
								},
								{
								"name": "10kV超华164开关柜体_温度传感器_TP20D35",
								"online": 1
								},
								{
								"name": "10kV超华164开关柜体_温度传感器_TP20D36",
								"online": 1
								},
								{
								"name": "10kV超华164开关柜体_温度传感器_TP20D1F",
								"online": 1
								},
								{
								"name": "10kV超华164开关柜体_温度传感器_TP20D20",
								"online": 1
								},
								{
								"name": "10kV超华164开关柜体_温度传感器_TP20D21",
								"online": 1
								},
								{
								"name": "10kV翠山166开关柜体_温湿度传感器_IRQ9896CC",
								"online": 1
								},
								{
								"name": "10kV翠山166开关柜体_温度传感器_TP20D2E",
								"online": 0
								},
								{
								"name": "10kV翠山166开关柜体_温度传感器_TP20D2F",
								"online": 0
								},
								{
								"name": "10kV翠山166开关柜体_温度传感器_TP20D30",
								"online": 0
								},
								{
								"name": "10kV翠山166开关柜体_温度传感器_TP20D25",
								"online": 0
								},
								{
								"name": "10kV翠山166开关柜体_温度传感器_TP20D26",
								"online": 0
								},
								{
								"name": "10kV翠山166开关柜体_温度传感器_TP20D27",
								"online": 0
								},
								{
								"name": "10kV9号电容器199开关柜体_温湿度传感器_IRQ9896C3",
								"online": 1
								},
								{
								"name": "10kV9号电容器199开关柜体_温度传感器_TP20D41",
								"online": 0
								},
								{
								"name": "10kV9号电容器199开关柜体_温度传感器_TP20D42",
								"online": 0
								},
								{
								"name": "10kV9号电容器199开关柜体_温度传感器_TP20D43",
								"online": 0
								},
								{
								"name": "10kV9号电容器199开关柜体_温度传感器_TP20D44",
								"online": 0
								},
								{
								"name": "10kV9号电容器199开关柜体_温度传感器_TP20D46",
								"online": 0
								},
								{
								"name": "10kV9号电容器199开关柜体_温度传感器_TP20D47",
								"online": 0
								},
								{
								"name": "10kVⅥ段母线压变1065手车_温湿度传感器_IRQ9896BA",
								"online": 1
								},
								{
								"name": "10kVⅥ段母线压变1065手车_温度传感器_TP20D8A",
								"online": 0
								},
								{
								"name": "10kVⅥ段母线压变1065手车_温度传感器_TP20D8B",
								"online": 0
								},
								{
								"name": "10kVⅥ段母线压变1065手车_温度传感器_TP20CD7",
								"online": 0
								},
								{
								"name": "3号接地变_温湿度传感器_IRQ9896D2",
								"online": 1
								},
								{
								"name": "10kV航天163开关柜体_温度传感器_TP20D31",
								"online": 1
								},
								{
								"name": "10kV航天163开关柜体_温度传感器_TP20D32",
								"online": 1
								},
								{
								"name": "10kV航天163开关柜体_温度传感器_TP20D33",
								"online": 1
								}
							],
						"sensorTypeCountList":[
								{
									sensorType: "温度传感器",
									count: 66
								},
								{
									sensorType: "温湿度传感器",
									count: 13
								}
							],
							"offlineCount": 29,
							"name": "2号汇聚节点",
							
							},
							{
							"children": [
								{
								"name": "10kV成业121开关柜体_温度传感器_TP20CCB",
								"online": 1
								},
								{
								"name": "10kV成业121开关柜体_温度传感器_TP20CCC",
								"online": 1
								},
								{
								"name": "10kV成业121开关柜体_温度传感器_TP20CCD",
								"online": 1
								},
								{
								"name": "10kV成业121开关柜体_温度传感器_TP20CCE",
								"online": 1
								},
								{
								"name": "10kV成业121开关柜体_温度传感器_TP20CCF",
								"online": 1
								},
								{
								"name": "10kV成业121开关柜体_温度传感器_TP20CD0",
								"online": 1
								},
								{
								"name": "10kV成业121开关柜体_温湿度传感器_IRQ989695",
								"online": 1
								},
								{
								"name": "10kV石埭122开关柜体_温度传感器_TP20CD1",
								"online": 1
								},
								{
								"name": "10kV石埭122开关柜体_温度传感器_TP20CD2",
								"online": 1
								},
								{
								"name": "10kV石埭122开关柜体_温度传感器_TP20CD3",
								"online": 1
								},
								{
								"name": "10kV石埭122开关柜体_温度传感器_TP20CD4",
								"online": 1
								},
								{
								"name": "10kV石埭122开关柜体_温度传感器_TP20CD5",
								"online": 1
								},
								{
								"name": "10kV石埭122开关柜体_温度传感器_TP20CD6",
								"online": 1
								},
								{
								"name": "10kV石埭122开关柜体_温湿度传感器_IRQ989699",
								"online": 1
								},
								{
								"name": "10kV海天123开关柜体_温湿度传感器_IRQ989696",
								"online": 1
								},
								{
								"name": "10kV海天123开关柜体_温度传感器_TP20D07",
								"online": 1
								},
								{
								"name": "10kV海天123开关柜体_温度传感器_TP20D08",
								"online": 1
								},
								{
								"name": "10kV海天123开关柜体_温度传感器_TP20D09",
								"online": 1
								},
								{
								"name": "10kV海天123开关柜体_温度传感器_TP20D0A",
								"online": 1
								},
								{
								"name": "10kV海天123开关柜体_温度传感器_TP20D0B",
								"online": 1
								},
								{
								"name": "10kV海天123开关柜体_温度传感器_TP20D0C",
								"online": 1
								},
								{
								"name": "10kV紫玉124开关柜体_温湿度传感器_IRQ98969C",
								"online": 1
								},
								{
								"name": "10kV紫玉124开关柜体_温度传感器_TP20D0D",
								"online": 1
								},
								{
								"name": "10kV紫玉124开关柜体_温度传感器_TP20D0E",
								"online": 0
								},
								{
								"name": "10kV紫玉124开关柜体_温度传感器_TP20D0F",
								"online": 0
								},
								{
								"name": "10kV紫玉124开关柜体_温度传感器_TP20D10",
								"online": 0
								},
								{
								"name": "10kV紫玉124开关柜体_温度传感器_TP20D11",
								"online": 1
								},
								{
								"name": "10kV紫玉124开关柜体_温度传感器_TP20D12",
								"online": 1
								},
								{
								"name": "10kV恒廷126开关柜体_温湿度传感器_IRQ989690",
								"online": 1
								},
								{
								"name": "10kV恒廷126开关柜体_温度传感器_TP20CC5",
								"online": 1
								},
								{
								"name": "10kV恒廷126开关柜体_温度传感器_TP20CC6",
								"online": 1
								},
								{
								"name": "10kV恒廷126开关柜体_温度传感器_TP20CC7",
								"online": 1
								},
								{
								"name": "10kV恒廷126开关柜体_温度传感器_TP20CC8",
								"online": 1
								},
								{
								"name": "10kV恒廷126开关柜体_温度传感器_TP20CC9",
								"online": 1
								},
								{
								"name": "10kV恒廷126开关柜体_温度传感器_TP20CCA",
								"online": 1
								},
								{
								"name": "10kV2号电容器192开关柜体_温湿度传感器_IRQ989692",
								"online": 1
								},
								{
								"name": "10kV2号电容器192开关柜体_温度传感器_TP20CBF",
								"online": 1
								},
								{
								"name": "10kV2号电容器192开关柜体_温度传感器_TP20CC0",
								"online": 1
								},
								{
								"name": "10kV2号电容器192开关柜体_温度传感器_TP20CC1",
								"online": 0
								},
								{
								"name": "10kV2号电容器192开关柜体_温度传感器_TP20CC2",
								"online": 1
								},
								{
								"name": "10kV2号电容器192开关柜体_温度传感器_TP20CC3",
								"online": 1
								},
								{
								"name": "10kV2号电容器192开关柜体_温度传感器_TP20CC4",
								"online": 1
								},
								{
								"name": "10kVⅡ段母线压变1025手车_温湿度传感器_IRQ989697",
								"online": 1
								},
								{
								"name": "10kVⅡ段母线压变1025手车_温度传感器_TP20C7B",
								"online": 0
								},
								{
								"name": "10kVⅡ段母线压变1025手车_温度传感器_TP20C7C",
								"online": 0
								},
								{
								"name": "10kVⅡ段母线压变1025手车_温度传感器_TP20C7D",
								"online": 0
								},
								{
								"name": "10kV吉艾125开关柜体_温湿度传感器_IRQ989691",
								"online": 1
								},
								{
								"name": "10kV吉艾125开关柜体_温度传感器_TP20D01",
								"online": 1
								},
								{
								"name": "10kV吉艾125开关柜体_温度传感器_TP20D02",
								"online": 1
								},
								{
								"name": "10kV吉艾125开关柜体_温度传感器_TP20D03",
								"online": 1
								},
								{
								"name": "10kV吉艾125开关柜体_温度传感器_TP20D04",
								"online": 1
								},
								{
								"name": "10kV吉艾125开关柜体_温度传感器_TP20D05",
								"online": 0
								},
								{
								"name": "10kV吉艾125开关柜体_温度传感器_TP20D06",
								"online": 1
								},
								{
								"name": "2号主变10kV侧103开关柜体_温湿度传感器_IRQ9896A0",
								"online": 1
								},
								{
								"name": "2号主变10kV侧103开关柜体_温度传感器_TP20C78",
								"online": 1
								},
								{
								"name": "2号主变10kV侧103开关柜体_温度传感器_TP20C8B",
								"online": 1
								},
								{
								"name": "2号主变10kV侧103开关柜体_温度传感器_TP20C6F",
								"online": 1
								},
								{
								"name": "2号主变10kV侧103开关柜体_温度传感器_TP20D89",
								"online": 1
								},
								{
								"name": "2号主变10kV侧103开关柜体_温度传感器_TP20D68",
								"online": 0
								},
								{
								"name": "2号主变10kV侧103开关柜体_温度传感器_TP20C4B",
								"online": 1
								},
								{
								"name": "10kV广信132开关柜体_温湿度传感器_IRQ9896A9",
								"online": 1
								},
								{
								"name": "10kV广信132开关柜体_温度传感器_TP20C43",
								"online": 1
								},
								{
								"name": "10kV广信132开关柜体_温度传感器_TP20C49",
								"online": 1
								},
								{
								"name": "10kV广信132开关柜体_温度传感器_TP20CDF",
								"online": 1
								},
								{
								"name": "10kV广信132开关柜体_温度传感器_TP20D59",
								"online": 1
								},
								{
								"name": "10kV广信132开关柜体_温度传感器_TP20D5A",
								"online": 1
								},
								{
								"name": "10kV广信132开关柜体_温度传感器_TP20D5B",
								"online": 1
								},
								{
								"name": "10kVⅢ段母线压变1035手车_温湿度传感器_IRQ98969E",
								"online": 1
								},
								{
								"name": "10kVⅢ段母线压变1035手车_温度传感器_TP20C87",
								"online": 0
								},
								{
								"name": "10kVⅢ段母线压变1035手车_温度传感器_TP20C88",
								"online": 0
								},
								{
								"name": "10kVⅢ段母线压变1035手车_温度传感器_TP20C89",
								"online": 0
								},
								{
								"name": "10kV4号电容器194开关柜体_温湿度传感器_IRQ98969A",
								"online": 1
								},
								{
								"name": "10kV4号电容器194开关柜体_温度传感器_TP20C38",
								"online": 0
								},
								{
								"name": "10kV4号电容器194开关柜体_温度传感器_TP20C39",
								"online": 0
								},
								{
								"name": "10kV4号电容器194开关柜体_温度传感器_TP20C3B",
								"online": 0
								},
								{
								"name": "10kV4号电容器194开关柜体_温度传感器_TP20C3D",
								"online": 0
								},
								{
								"name": "10kV4号电容器194开关柜体_温度传感器_TP20C3F",
								"online": 0
								},
								{
								"name": "10kV4号电容器194开关柜体_温度传感器_TP20C41",
								"online": 0
								},
								{
								"name": "10kV文瑞131开关柜体_温湿度传感器_IRQ9896AD",
								"online": 1
								},
								{
								"name": "10kV文瑞131开关柜体_温度传感器_TP20C4C",
								"online": 1
								},
								{
								"name": "10kV文瑞131开关柜体_温度传感器_TP20CBE",
								"online": 1
								},
								{
								"name": "10kV文瑞131开关柜体_温度传感器_TP20D65",
								"online": 1
								},
								{
								"name": "10kV文瑞131开关柜体_温度传感器_TP20C47",
								"online": 1
								},
								{
								"name": "10kV文瑞131开关柜体_温度传感器_TP20C4A",
								"online": 1
								},
								{
								"name": "10kV文瑞131开关柜体_温度传感器_TP20C4D",
								"online": 1
								},
								{
								"name": "10kV碧桂134开关柜体_温湿度传感器_IRQ9896A6",
								"online": 1
								},
								{
								"name": "10kV碧桂134开关柜体_温度传感器_TP20C69",
								"online": 1
								},
								{
								"name": "10kV碧桂134开关柜体_温度传感器_TP20C6A",
								"online": 1
								},
								{
								"name": "10kV碧桂134开关柜体_温度传感器_TP20C6B",
								"online": 1
								},
								{
								"name": "10kV碧桂134开关柜体_温度传感器_TP20D60",
								"online": 1
								},
								{
								"name": "10kV碧桂134开关柜体_温度传感器_TP20D61",
								"online": 1
								},
								{
								"name": "10kV碧桂134开关柜体_温度传感器_TP20D62",
								"online": 1
								},
								{
								"name": "10kVⅡ、Ⅲ段分段120开关柜体_温湿度传感器_IRQ989698",
								"online": 1
								},
								{
								"name": "10kVⅡ、Ⅲ段分段120开关柜体_温度传感器_TP20D50",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段120开关柜体_温度传感器_TP20C8E",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段120开关柜体_温度传感器_TP20C8F",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段120开关柜体_温度传感器_TP20C90",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段120开关柜体_温度传感器_TP20D52",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段120开关柜体_温度传感器_TP20D51",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段1201隔离手车柜体_温湿度传感器_IRQ989688",
								"online": 1
								},
								{
								"name": "10kVⅡ、Ⅲ段分段1201隔离手车柜体_温度传感器_TP20C91",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段1201隔离手车柜体_温度传感器_TP20C92",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段1201隔离手车柜体_温度传感器_TP20C93",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段1201隔离手车柜体_温度传感器_TP20C84",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段1201隔离手车柜体_温度传感器_TP20C85",
								"online": 0
								},
								{
								"name": "10kVⅡ、Ⅲ段分段1201隔离手车柜体_温度传感器_TP20C86",
								"online": 0
								},
								{
								"name": "10kV3号电容器193开关柜体_温度传感器_TP20CEF",
								"online": 1
								},
								{
								"name": "10kV3号电容器193开关柜体_温度传感器_TP20CF0",
								"online": 1
								},
								{
								"name": "10kV3号电容器193开关柜体_温度传感器_TP20CF1",
								"online": 1
								},
								{
								"name": "10kV3号电容器193开关柜体_温度传感器_TP20CF2",
								"online": 1
								},
								{
								"name": "10kV3号电容器193开关柜体_温度传感器_TP20CF3",
								"online": 1
								},
								{
								"name": "10kV3号电容器193开关柜体_温度传感器_TP20CF4",
								"online": 1
								},
								{
								"name": "10kV3号电容器193开关柜体_温湿度传感器_IRQ989693",
								"online": 1
								},
								{
								"name": "10kV新厚133开关柜体_温湿度传感器_IRQ9896A8",
								"online": 1
								},
								{
								"name": "10kV新厚133开关柜体_温度传感器_TP20D5C",
								"online": 1
								},
								{
								"name": "10kV新厚133开关柜体_温度传感器_TP20D5D",
								"online": 1
								},
								{
								"name": "10kV新厚133开关柜体_温度传感器_TP20D5E",
								"online": 1
								},
								{
								"name": "10kV新厚133开关柜体_温度传感器_TP20C66",
								"online": 1
								},
								{
								"name": "10kV新厚133开关柜体_温度传感器_TP20C67",
								"online": 1
								},
								{
								"name": "10kV新厚133开关柜体_温度传感器_TP20C68",
								"online": 1
								},
								{
								"name": "10kV万泉135开关柜体_温湿度传感器_IRQ9896B2",
								"online": 1
								},
								{
								"name": "10kV万泉135开关柜体_温度传感器_TP20D63",
								"online": 1
								},
								{
								"name": "10kV万泉135开关柜体_温度传感器_TP20D64",
								"online": 1
								},
								{
								"name": "10kV万泉135开关柜体_温度传感器_TP20C48",
								"online": 1
								},
								{
								"name": "10kV万泉135开关柜体_温度传感器_TP20D53",
								"online": 1
								},
								{
								"name": "10kV万泉135开关柜体_温度传感器_TP20D54",
								"online": 1
								},
								{
								"name": "10kV万泉135开关柜体_温度传感器_TP20D55",
								"online": 1
								},
								{
								"name": "10kV润锡136开关柜体_温湿度传感器_IRQ9896B7",
								"online": 1
								},
								{
								"name": "10kV润锡136开关柜体_温度传感器_TP20D56",
								"online": 1
								},
								{
								"name": "10kV润锡136开关柜体_温度传感器_TP20D57",
								"online": 1
								},
								{
								"name": "10kV润锡136开关柜体_温度传感器_TP20D58",
								"online": 1
								},
								{
								"name": "10kV润锡136开关柜体_温度传感器_TP20D4C",
								"online": 1
								},
								{
								"name": "10kV润锡136开关柜体_温度传感器_TP20D4D",
								"online": 1
								},
								{
								"name": "10kV润锡136开关柜体_温度传感器_TP20D4E",
								"online": 1
								},
								{
								"name": "1号主变10kV侧102开关柜体_温湿度传感器_IRQ989683",
								"online": 1
								},
								{
								"name": "1号主变10kV侧102开关柜体_温度传感器_TP20BDB",
								"online": 1
								},
								{
								"name": "1号主变10kV侧102开关柜体_温度传感器_TP20BDC",
								"online": 1
								},
								{
								"name": "1号主变10kV侧102开关柜体_温度传感器_TP20BDD",
								"online": 1
								},
								{
								"name": "1号主变10kV侧102开关柜体_温度传感器_TP20BDE",
								"online": 1
								},
								{
								"name": "1号主变10kV侧102开关柜体_温度传感器_TP20BDF",
								"online": 1
								},
								{
								"name": "1号主变10kV侧102开关柜体_温度传感器_TP20BE0",
								"online": 1
								},
								{
								"name": "1号主变_温湿度传感器_IRQ989685",
								"online": 1
								},
								{
								"name": "1号主变_温度传感器_TP20BE1",
								"online": 1
								},
								{
								"name": "1号主变_温度传感器_TP20BE2",
								"online": 1
								},
								{
								"name": "1号主变_温度传感器_TP20BE3",
								"online": 1
								},
								{
								"name": "1号主变_温度传感器_TP20BE6",
								"online": 1
								},
								{
								"name": "1号主变_温度传感器_TP20BE7",
								"online": 1
								},
								{
								"name": "1号主变_温度传感器_TP20BE8",
								"online": 1
								},
								{
								"name": "温湿度传感器_IRQ9896CE",
								"online": 1
								}
							],
						"sensorTypeCountList":[
								{
									sensorType: "温度传感器",
									count: 126
								},
								{
									sensorType: "温湿度传感器",
									count: 23
								}
							],
							"offlineCount": 30,
							"name": "3号汇聚节点",
							},
							{
							"children": [
								{
								"name": "10kV洋泾143开关柜体_温度传感器_TP20C72",
								"online": 0
								},
								{
								"name": "10kV洋泾143开关柜体_温度传感器_TP20C73",
								"online": 1
								},
								{
								"name": "10kV洋泾143开关柜体_温度传感器_TP20C74",
								"online": 1
								},
								{
								"name": "10kV洋泾143开关柜体_温度传感器_TP20C75",
								"online": 1
								},
								{
								"name": "10kV洋泾143开关柜体_温度传感器_TP20C76",
								"online": 1
								},
								{
								"name": "10kV洋泾143开关柜体_温度传感器_TP20C77",
								"online": 1
								},
								{
								"name": "10kV洋泾143开关柜体_温湿度传感器_IRQ9896AB",
								"online": 1
								},
								{
								"name": "10kV备用145开关柜体_温湿度传感器_IRQ9896AA",
								"online": 1
								},
								{
								"name": "10kV备用145开关柜体_温度传感器_TP20D13",
								"online": 0
								},
								{
								"name": "10kV备用145开关柜体_温度传感器_TP20D14",
								"online": 0
								},
								{
								"name": "10kV备用145开关柜体_温度传感器_TP20D15",
								"online": 0
								},
								{
								"name": "10kV备用145开关柜体_温度传感器_TP20D16",
								"online": 0
								},
								{
								"name": "10kV备用145开关柜体_温度传感器_TP20D17",
								"online": 0
								},
								{
								"name": "10kV备用145开关柜体_温度传感器_TP20D18",
								"online": 0
								},
								{
								"name": "2号接地变182开关柜体_温湿度传感器_IRQ9896A1",
								"online": 1
								},
								{
								"name": "2号接地变182开关柜体_温度传感器_TP20CF5",
								"online": 0
								},
								{
								"name": "2号接地变182开关柜体_温度传感器_TP20CF6",
								"online": 0
								},
								{
								"name": "2号接地变182开关柜体_温度传感器_TP20CF7",
								"online": 0
								},
								{
								"name": "2号接地变182开关柜体_温度传感器_TP20CF8",
								"online": 0
								},
								{
								"name": "2号接地变182开关柜体_温度传感器_TP20CF9",
								"online": 0
								},
								{
								"name": "2号接地变182开关柜体_温度传感器_TP20CFA",
								"online": 0
								},
								{
								"name": "10kV5号电容器195开关柜体_温湿度传感器_IRQ9896A4",
								"online": 1
								},
								{
								"name": "10kV5号电容器195开关柜体_温度传感器_TP20C4E",
								"online": 0
								},
								{
								"name": "10kV锋铁141开关柜体_温度传感器_TP20CE1",
								"online": 1
								},
								{
								"name": "10kV锋铁141开关柜体_温度传感器_TP20CE2",
								"online": 1
								},
								{
								"name": "10kV锋铁141开关柜体_温度传感器_TP20CE3",
								"online": 1
								},
								{
								"name": "10kV锋铁141开关柜体_温度传感器_TP20CE4",
								"online": 1
								},
								{
								"name": "10kV锋铁141开关柜体_温度传感器_TP20CE5",
								"online": 1
								},
								{
								"name": "10kV锋铁141开关柜体_温度传感器_TP20CE6",
								"online": 1
								},
								{
								"name": "10kV锋铁141开关柜体_温湿度传感器_IRQ9896A5",
								"online": 1
								},
								{
								"name": "10kV兴吴146开关柜体_温湿度传感器_IRQ9896AC",
								"online": 1
								},
								{
								"name": "10kV兴吴146开关柜体_温度传感器_TP20C5A",
								"online": 1
								},
								{
								"name": "10kV兴吴146开关柜体_温度传感器_TP20C5B",
								"online": 1
								},
								{
								"name": "10kV兴吴146开关柜体_温度传感器_TP20C5C",
								"online": 1
								},
								{
								"name": "10kV兴吴146开关柜体_温度传感器_TP20C5D",
								"online": 1
								},
								{
								"name": "10kV兴吴146开关柜体_温度传感器_TP20C5E",
								"online": 1
								},
								{
								"name": "10kV兴吴146开关柜体_温度传感器_TP20C5F",
								"online": 1
								},
								{
								"name": "10kV5号电容器195开关柜体_温度传感器_TP20C4F",
								"online": 0
								},
								{
								"name": "2号主变10kV侧104开关柜体_温湿度传感器_IRQ9896B8",
								"online": 1
								},
								{
								"name": "2号主变10kV侧104开关柜体_温度传感器_TP20CE7",
								"online": 1
								},
								{
								"name": "2号主变10kV侧104开关柜体_温度传感器_TP20C42",
								"online": 1
								},
								{
								"name": "2号主变10kV侧104开关柜体_温度传感器_TP20D67",
								"online": 1
								},
								{
								"name": "2号主变10kV侧104开关柜体_温度传感器_TP20C44",
								"online": 1
								},
								{
								"name": "2号主变10kV侧104开关柜体_温度传感器_TP20C46",
								"online": 1
								},
								{
								"name": "2号主变10kV侧104开关柜体_温度传感器_TP20D66",
								"online": 0
								},
								{
								"name": "10kV亚冠152开关柜体_温度传感器_TP20D82",
								"online": 1
								},
								{
								"name": "10kV亚冠152开关柜体_温度传感器_TP20D83",
								"online": 1
								},
								{
								"name": "10kV亚冠152开关柜体_温度传感器_TP20D84",
								"online": 1
								},
								{
								"name": "10kV浩锋153开关柜体_温度传感器_TP20CFB",
								"online": 1
								},
								{
								"name": "10kV浩锋153开关柜体_温度传感器_TP20CFC",
								"online": 1
								},
								{
								"name": "10kV浩锋153开关柜体_温度传感器_TP20CFD",
								"online": 1
								},
								{
								"name": "10kV浩锋153开关柜体_温度传感器_TP20CFE",
								"online": 1
								},
								{
								"name": "10kV浩锋153开关柜体_温度传感器_TP20CFF",
								"online": 1
								},
								{
								"name": "10kV浩锋153开关柜体_温度传感器_TP20D00",
								"online": 1
								},
								{
								"name": "10kV浩锋153开关柜体_温湿度传感器_IRQ9896BB",
								"online": 1
								},
								{
								"name": "10kV河西154开关柜体_温湿度传感器_IRQ9896C5",
								"online": 1
								},
								{
								"name": "10kV河西154开关柜体_温度传感器_TP20CAC",
								"online": 1
								},
								{
								"name": "10kV河西154开关柜体_温度传感器_TP20CAD",
								"online": 1
								},
								{
								"name": "10kV河西154开关柜体_温度传感器_TP20CAF",
								"online": 1
								},
								{
								"name": "10kV河西154开关柜体_温度传感器_TP20C9A",
								"online": 1
								},
								{
								"name": "10kV河西154开关柜体_温度传感器_TP20C9B",
								"online": 1
								},
								{
								"name": "10kV河西154开关柜体_温度传感器_TP20C9C",
								"online": 1
								},
								{
								"name": "10kV先卫155开关柜体_温湿度传感器_IRQ9896C6",
								"online": 1
								},
								{
								"name": "10kV先卫155开关柜体_温度传感器_TP20C9D",
								"online": 1
								},
								{
								"name": "10kV先卫155开关柜体_温度传感器_TP20C9E",
								"online": 1
								},
								{
								"name": "10kV先卫155开关柜体_温度传感器_TP20C9F",
								"online": 1
								},
								{
								"name": "10kV先卫155开关柜体_温度传感器_TP20C94",
								"online": 1
								},
								{
								"name": "10kV6号电容器196开关柜体_温湿度传感器_IRQ9896B1",
								"online": 1
								},
								{
								"name": "10kV6号电容器196开关柜体_温度传感器_TP20C60",
								"online": 0
								},
								{
								"name": "10kV6号电容器196开关柜体_温度传感器_TP20C61",
								"online": 0
								},
								{
								"name": "10kV6号电容器196开关柜体_温度传感器_TP20C62",
								"online": 0
								},
								{
								"name": "10kV6号电容器196开关柜体_温度传感器_TP20C63",
								"online": 0
								},
								{
								"name": "10kV6号电容器196开关柜体_温度传感器_TP20C64",
								"online": 0
								},
								{
								"name": "10kV6号电容器196开关柜体_温度传感器_TP20C65",
								"online": 0
								},
								{
								"name": "10kVⅣ、Ⅴ段分段130开关柜体_温湿度传感器_IRQ98969B",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段130开关柜体_温度传感器_TP20C54",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段130开关柜体_温度传感器_TP20C55",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段130开关柜体_温度传感器_TP20C56",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段130开关柜体_温度传感器_TP20C57",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段130开关柜体_温度传感器_TP20C58",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段130开关柜体_温度传感器_TP20C59",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段1301隔离手车柜体_温度传感器_TP20C7E",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段1301隔离手车柜体_温度传感器_TP20C7F",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段1301隔离手车柜体_温度传感器_TP20C80",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段1301隔离手车柜体_温度传感器_TP20C81",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段1301隔离手车柜体_温度传感器_TP20C82",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段1301隔离手车柜体_温度传感器_TP20C83",
								"online": 1
								},
								{
								"name": "10kVⅣ、Ⅴ段分段1301隔离手车柜体_温湿度传感器_IRQ9896A3",
								"online": 1
								},
								{
								"name": "2号主变_温湿度传感器_IRQ9896B9",
								"online": 1
								},
								{
								"name": "2号主变_温度传感器_TP20C70",
								"online": 1
								},
								{
								"name": "2号主变_温度传感器_TP20D4A",
								"online": 1
								},
								{
								"name": "2号主变_温度传感器_TP20C79",
								"online": 1
								},
								{
								"name": "2号主变_温度传感器_TP20C71",
								"online": 1
								},
								{
								"name": "2号主变_温度传感器_TP20D4B",
								"online": 0
								},
								{
								"name": "2号主变_温度传感器_TP20C8C",
								"online": 1
								},
								{
								"name": "10kV澳洋151开关柜体_温湿度传感器_IRQ9896C2",
								"online": 1
								},
								{
								"name": "10kV澳洋151开关柜体_温度传感器_TP20CA6",
								"online": 1
								},
								{
								"name": "10kV澳洋151开关柜体_温度传感器_TP20CA7",
								"online": 1
								},
								{
								"name": "10kV澳洋151开关柜体_温度传感器_TP20CA8",
								"online": 1
								},
								{
								"name": "10kV澳洋151开关柜体_温度传感器_TP20CA9",
								"online": 1
								},
								{
								"name": "10kV澳洋151开关柜体_温度传感器_TP20CAA",
								"online": 1
								},
								{
								"name": "10kV澳洋151开关柜体_温度传感器_TP20CAB",
								"online": 1
								},
								{
								"name": "10kV亚冠152开关柜体_温湿度传感器_IRQ9896BC",
								"online": 1
								},
								{
								"name": "10kV亚冠152开关柜体_温度传感器_TP20CA0",
								"online": 1
								},
								{
								"name": "10kV亚冠152开关柜体_温度传感器_TP20CA1",
								"online": 1
								},
								{
								"name": "10kV亚冠152开关柜体_温度传感器_TP20CA2",
								"online": 1
								},
								{
								"name": "10kV亚冠152开关柜体_温度传感器_TP20CA3",
								"online": 1
								},
								{
								"name": "10kV杰利142开关柜体_温湿度传感器_IRQ9896A2",
								"online": 1
								},
								{
								"name": "10kV杰利142开关柜体_温度传感器_TP20CE9",
								"online": 1
								},
								{
								"name": "10kV杰利142开关柜体_温度传感器_TP20CEA",
								"online": 1
								},
								{
								"name": "10kV杰利142开关柜体_温度传感器_TP20CEB",
								"online": 1
								},
								{
								"name": "10kV杰利142开关柜体_温度传感器_TP20CEC",
								"online": 1
								},
								{
								"name": "10kV杰利142开关柜体_温度传感器_TP20CED",
								"online": 1
								},
								{
								"name": "10kV杰利142开关柜体_温度传感器_TP20CEE",
								"online": 1
								},
								{
								"name": "10kV豪景144开关柜体_温湿度传感器_IRQ9896AE",
								"online": 1
								},
								{
								"name": "10kV豪景144开关柜体_温度传感器_TP20CD9",
								"online": 1
								},
								{
								"name": "10kV豪景144开关柜体_温度传感器_TP20CDA",
								"online": 1
								},
								{
								"name": "10kV豪景144开关柜体_温度传感器_TP20CDB",
								"online": 1
								},
								{
								"name": "10kV豪景144开关柜体_温度传感器_TP20CDC",
								"online": 1
								},
								{
								"name": "10kV豪景144开关柜体_温度传感器_TP20CDD",
								"online": 1
								},
								{
								"name": "10kV豪景144开关柜体_温度传感器_TP20CDE",
								"online": 1
								},
								{
								"name": "10kV5号电容器195开关柜体_温度传感器_TP20C50",
								"online": 0
								},
								{
								"name": "10kV5号电容器195开关柜体_温度传感器_TP20C51",
								"online": 0
								},
								{
								"name": "10kV5号电容器195开关柜体_温度传感器_TP20C52",
								"online": 0
								},
								{
								"name": "10kV5号电容器195开关柜体_温度传感器_TP20C53",
								"online": 0
								},
								{
								"name": "10kVⅣ段母线压变1045手车_温湿度传感器_IRQ9896B0",
								"online": 1
								},
								{
								"name": "10kVⅣ段母线压变1045手车_温度传感器_TP20C6C",
								"online": 0
								},
								{
								"name": "10kVⅣ段母线压变1045手车_温度传感器_TP20C6D",
								"online": 0
								},
								{
								"name": "10kVⅣ段母线压变1045手车_温度传感器_TP20C6E",
								"online": 0
								},
								{
								"name": "10kV亚冠152开关柜体_温度传感器_TP20CA4",
								"online": 1
								},
								{
								"name": "10kV亚冠152开关柜体_温度传感器_TP20CA5",
								"online": 1
								},
								{
								"name": "10kV先卫155开关柜体_温度传感器_TP20C95",
								"online": 1
								},
								{
								"name": "10kV先卫155开关柜体_温度传感器_TP20C96",
								"online": 1
								},
								{
								"name": "10kV备用156开关柜体_温湿度传感器_IRQ9896C0",
								"online": 1
								},
								{
								"name": "10kV备用156开关柜体_温度传感器_TP20C97",
								"online": 0
								},
								{
								"name": "10kV备用156开关柜体_温度传感器_TP20C98",
								"online": 0
								},
								{
								"name": "10kV备用156开关柜体_温度传感器_TP20C99",
								"online": 0
								},
								{
								"name": "10kV备用156开关柜体_温度传感器_TP20CB2",
								"online": 0
								},
								{
								"name": "10kV备用156开关柜体_温度传感器_TP20CB3",
								"online": 0
								},
								{
								"name": "10kV备用156开关柜体_温度传感器_TP20CB4",
								"online": 0
								},
								{
								"name": "10kVⅤ段母线压变1055手车_温湿度传感器_IRQ9896C4",
								"online": 1
								},
								{
								"name": "10kVⅤ段母线压变1055手车_温度传感器_TP20D7C",
								"online": 0
								},
								{
								"name": "10kVⅤ段母线压变1055手车_温度传感器_TP20D7D",
								"online": 0
								},
								{
								"name": "10kVⅤ段母线压变1055手车_温度传感器_TP20D7E",
								"online": 0
								},
								{
								"name": "温湿度传感器_IRQ9896CD",
								"online": 1
								},
								{
								"name": "10kV7号电容器197开关柜体_温湿度传感器_IRQ9896C1",
								"online": 1
								},
								{
								"name": "10kV7号电容器197开关柜体_温度传感器_TP20D28",
								"online": 0
								},
								{
								"name": "10kV7号电容器197开关柜体_温度传感器_TP20D29",
								"online": 0
								},
								{
								"name": "10kV7号电容器197开关柜体_温度传感器_TP20D2A",
								"online": 0
								},
								{
								"name": "10kV7号电容器197开关柜体_温度传感器_TP20D38",
								"online": 0
								},
								{
								"name": "10kV7号电容器197开关柜体_温度传感器_TP20D39",
								"online": 0
								},
								{
								"name": "10kV7号电容器197开关柜体_温度传感器_TP20D3A",
								"online": 0
								},
								{
								"name": "3号接地变183开关柜体_温湿度传感器_IRQ9896BE",
								"online": 1
								},
								{
								"name": "3号接地变183开关柜体_温度传感器_TP20D48",
								"online": 0
								},
								{
								"name": "3号接地变183开关柜体_温度传感器_TP20D49",
								"online": 0
								},
								{
								"name": "3号接地变183开关柜体_温度传感器_TP20D37",
								"online": 0
								},
								{
								"name": "3号接地变183开关柜体_温度传感器_TP20C32",
								"online": 0
								},
								{
								"name": "3号接地变183开关柜体_温度传感器_TP20C35",
								"online": 0
								},
								{
								"name": "3号接地变183开关柜体_温度传感器_TP20CB0",
								"online": 0
								}
							],
						"sensorTypeCountList":[
								{
									sensorType: "温度传感器",
									count: 135
								},
								{
									sensorType: "温湿度传感器",
									count: 24
								}
							],
							"offlineCount": 51,
							"name": "4号汇聚节点",
							},
							{
							"children": [
								{
								"name": "1号接地变_高压侧A相_无线温度传感器_WS13B8",
								"online": 1
								},
								{
								"name": "1号接地变_高压侧B相_无线温度传感器_WS13E3",
								"online": 1
								},
								{
								"name": "1号接地变_高压侧C相_无线温度传感器_WS66E3",
								"online": 1
								},
								{
								"name": "1号接地变_低压侧A相_无线温度传感器_WS68BF",
								"online": 1
								},
								{
								"name": "1号接地变_低压侧B相_无线温度传感器_WS68FB",
								"online": 1
								},
								{
								"name": "1号接地变_低压侧C相_无线温度传感器_WS12C5",
								"online": 1
								},
								{
								"name": "1号接地变_低压侧N相_无线温度传感器_WS674A",
								"online": 1
								},
								{
								"name": "1号接地变_接地电阻中性侧_无线温度传感器_WS6E00",
								"online": 1
								},
								{
								"name": "1号接地变_接地电阻接地侧_无线温度传感器_WS100D",
								"online": 1
								},
								{
								"name": "2号接地变_高压侧A相_无线温度传感器_WS6979",
								"online": 1
								},
								{
								"name": "2号接地变_高压侧B相_无线温度传感器_WS68AE",
								"online": 1
								},
								{
								"name": "2号接地变_高压侧C相_无线温度传感器_WS1017",
								"online": 1
								},
								{
								"name": "2号接地变_低压侧A相_无线温度传感器_WS1184",
								"online": 1
								},
								{
								"name": "2号接地变_低压侧B相_无线温度传感器_WS6EBA",
								"online": 1
								},
								{
								"name": "2号接地变_低压侧C相_无线温度传感器_WS699E",
								"online": 1
								},
								{
								"name": "2号接地变_低压侧N相_无线温度传感器_WS10C7",
								"online": 1
								},
								{
								"name": "2号接地变_接地电阻中性侧_无线温度传感器_WS6659",
								"online": 1
								},
								{
								"name": "2号接地变_接地电阻接地侧_无线温度传感器_WS6AA4",
								"online": 1
								}
							],
						"sensorTypeCountList":[
								{
									sensorType: "温度传感器",
									count: 18
								}
							],
							"offlineCount": 0,
							"name": "5号汇聚节点",
							},
							{
							"children": [
								{
								"name": "3号接地变_高压侧A相_无线温度传感器_WS62D3",
								"online": 1
								},
								{
								"name": "3号接地变_高压侧B相_无线温度传感器_WS6426",
								"online": 1
								},
								{
								"name": "3号接地变_高压侧C相_无线温度传感器_WS6715",
								"online": 1
								},
								{
								"name": "3号接地变_低压侧A相_无线温度传感器_WS12F0",
								"online": 1
								},
								{
								"name": "3号接地变_低压侧B相_无线温度传感器_WS6E02",
								"online": 1
								},
								{
								"name": "3号接地变_低压侧C相_无线温度传感器_WS11D3",
								"online": 1
								},
								{
								"name": "3号接地变_低压侧N相_无线温度传感器_WS697A",
								"online": 1
								},
								{
								"name": "3号接地变_接地电阻中性侧_无线温度传感器_WS6B80",
								"online": 1
								},
								{
								"name": "3号接地变_接地电阻接地侧_无线温度传感器_WS1167",
								"online": 1
								}
							],
						"sensorTypeCountList":[
								{
									sensorType: "温度传感器",
									count: 9
								}
							],
							"offlineCount": 0,
							"name": "6号汇聚节点",
							},
							{
							"children": [
								{
								"name": "1号电容器_高压侧A相_无线温度传感器_WS6CC8",
								"online": 1
								},
								{
								"name": "1号电容器_高压侧B相_无线温度传感器_WS6E98",
								"online": 1
								},
								{
								"name": "1号电容器_高压侧C相_无线温度传感器_WS6430",
								"online": 1
								},
								{
								"name": "1号电容器_低压侧A相_无线温度传感器_WS642D",
								"online": 1
								},
								{
								"name": "1号电容器_低压侧B相_无线温度传感器_WS691D",
								"online": 1
								},
								{
								"name": "1号电容器_低压侧C相_无线温度传感器_WS6CA2",
								"online": 1
								},
								{
								"name": "2号电容器_高压侧A相_无线温度传感器_WS6568",
								"online": 1
								},
								{
								"name": "2号电容器_高压侧B相_无线温度传感器_WS1178",
								"online": 1
								},
								{
								"name": "2号电容器_高压侧C相_无线温度传感器_WS629C",
								"online": 1
								},
								{
								"name": "2号电容器_低压侧A相_无线温度传感器_WS6678",
								"online": 1
								},
								{
								"name": "2号电容器_低压侧B相_无线温度传感器_WS10B6",
								"online": 1
								},
								{
								"name": "2号电容器_低压侧C相_无线温度传感器_WS6D50",
								"online": 1
								},
								{
								"name": "3号电容器_高压侧A相_无线温度传感器_WS11B0",
								"online": 1
								},
								{
								"name": "3号电容器_高压侧B相_无线温度传感器_WS13CF",
								"online": 1
								},
								{
								"name": "3号电容器_高压侧C相_无线温度传感器_WS629F",
								"online": 1
								},
								{
								"name": "3号电容器_低压侧A相_无线温度传感器_WS6F32",
								"online": 1
								},
								{
								"name": "3号电容器_低压侧B相_无线温度传感器_WS691B",
								"online": 1
								},
								{
								"name": "3号电容器_低压侧C相_无线温度传感器_WS6A9D",
								"online": 1
								},
								{
								"name": "1号电容器室_电容柜内壁_无线温湿度传感器_WS83D1",
								"online": 1
								},
								{
								"name": "2号电容器室_电容柜内壁_无线温湿度传感器_WS8432",
								"online": 1
								},
								{
								"name": "3号电容器室_电容柜内壁_无线温湿度传感器_WS83C9",
								"online": 1
								}
							],
						"sensorTypeCountList":[
								{
									sensorType: "温度传感器",
									count: 18
								},
								{
									sensorType: "温湿度传感器",
									count: 3
								}
							],
							"offlineCount": 0,
							"name": "7号汇聚节点",
							},
							{
							"children": [
								{
								"name": "4号电容器_高压侧A相_无线温度传感器_WS6460",
								"online": 1
								},
								{
								"name": "4号电容器_高压侧B相_无线温度传感器_WS64F3",
								"online": 1
								},
								{
								"name": "4号电容器_高压侧C相_无线温度传感器_WS1197",
								"online": 1
								},
								{
								"name": "4号电容器_低压侧A相_无线温度传感器_WS685C",
								"online": 1
								},
								{
								"name": "4号电容器_低压侧B相_无线温度传感器_WS13E6",
							"online": 1
							},
							{
							"name": "4号电容器_低压侧C相_无线温度传感器_WS12F5",
							"online": 1
							},
							{
							"name": "5号电容器_高压侧A相_无线温度传感器_WS1366",
							"online": 1
							},
							{
							"name": "5号电容器_高压侧B相_无线温度传感器_WS6E07",
							"online": 1
							},
							{
							"name": "5号电容器_高压侧C相_无线温度传感器_WS6CCA",
							"online": 1
							},
							{
							"name": "5号电容器_低压侧A相_无线温度传感器_WS13B6",
							"online": 1
							},
							{
							"name": "5号电容器_低压侧B相_无线温度传感器_WS13D0",
							"online": 1
							},
							{
							"name": "5号电容器_低压侧C相_无线温度传感器_WS69EF",
							"online": 1
							},
							{
							"name": "4号电容器室_电容柜内壁_无线温湿度传感器_WS83EE",
							"online": 1
							},
							{
							"name": "5号电容器室_电容柜内壁_无线温湿度传感器_WS83E1",
							"online": 1
							}
						],
					"sensorTypeCountList":[
							{
								sensorType: "温度传感器",
								count: 12
							},
							{
								sensorType: "温湿度传感器",
								count: 2
							}
						],
						"offlineCount": 0,
						"name": "8号汇聚节点",
						},
						{
						"children": [
							{
							"name": "6号电容器_高压侧A相_无线温度传感器_WS13A2",
							"online": 1
							},
							{
							"name": "6号电容器_高压侧B相_无线温度传感器_WS657A",
							"online": 1
							},
							{
							"name": "6号电容器_高压侧C相_无线温度传感器_WS647D",
							"online": 1
							},
							{
							"name": "6号电容器_低压侧A相_无线温度传感器_WS613A",
							"online": 1
							},
							{
							"name": "6号电容器_低压侧B相_无线温度传感器_WS12EA",
							"online": 1
							},
							{
							"name": "6号电容器_低压侧C相_无线温度传感器_WS13CA",
							"online": 1
							},
							{
							"name": "6号电容器室_电容柜内壁_无线温湿度传感器_WS842A",
							"online": 1
							},
							{
							"name": "六号电容器组_C6_形变温度传感器_WS90A1",
							"online": 1
							},
							{
							"name": "六号电容器组_C5_形变温度传感器_WS91E1",
							"online": 1
							},
							{
							"name": "六号电容器组_C4_形变温度传感器_WS90C7",
							"online": 1
							},
							{
							"name": "六号电容器组_C3_形变温度传感器_WS93D3",
							"online": 1
							},
							{
							"name": "六号电容器组_C2_形变温度传感器_WS93DF",
							"online": 1
						},
						{
						"name": "六号电容器组_C1_形变温度传感器_WS9420",
						"online": 1
						},
						{
						"name": "六号电容器组_B6_形变温度传感器_WS93AC",
						"online": 1
						},
						{
						"name": "六号电容器组_B5_形变温度传感器_WS91BF",
						"online": 1
						},
						{
						"name": "六号电容器组_B4_形变温度传感器_WS93F6",
						"online": 1
						},
						{
						"name": "六号电容器组_B3_形变温度传感器_WS9268",
						"online": 1
						},
						{
						"name": "六号电容器组_B2_形变温度传感器_WS9424",
						"online": 1
						},
						{
						"name": "六号电容器组_B1_形变温度传感器_WS91C2",
						"online": 1
						},
						{
						"name": "六号电容器组_A6_形变温度传感器_WS92D9",
						"online": 1
						},
						{
						"name": "六号电容器组_A5_形变温度传感器_WS9262",
						"online": 1
						},
						{
						"name": "六号电容器组_A4_形变温度传感器_WS920B",
						"online": 1
						},
						{
						"name": "六号电容器组_A3_形变温度传感器_WS93C2",
						"online": 1
						},
						{
						"name": "六号电容器组_A2_形变温度传感器_WS90D9",
						"online": 1
						},
						{
						"name": "六号电容器组_A1_形变温度传感器_WS90C2",
						"online": 1
						}
					],
				"sensorTypeCountList":[
						{
							sensorType: "温度传感器",
							count: 6
						},
						{
							sensorType: "形变传感器",
							count: 18
						},
						{
							sensorType: "温湿度传感器",
							count: 1
						}
					],
					"offlineCount": 0,
					"name": "9号汇聚节点",
					},
					{
					"children": [
						{
						"name": "北墙电缆进出线_地面1号_无线水浸传感器_WSA13D",
						"online": 1
						},
						{
						"name": "北墙电缆进出线_地面2号_无线水浸传感器_WSA140",
						"online": 1
						},
						{
						"name": "北墙电缆进出线_地面3号_无线水浸传感器_WSA168",
						"online": 1
						},
						{
						"name": "北墙电缆进出线_地面4号_无线水浸传感器_WSA14E",
						"online": 1
						},
						{
						"name": "南墙电缆进出线_地面1号_无线水浸传感器_WSA15F",
						"online": 1
						},
						{
						"name": "南墙电缆进出线_地面2号_无线水浸传感器_WSA138",
						"online": 1
						},
						{
						"name": "南墙电缆进出线_地面3号_无线水浸传感器_WSA16A",
						"online": 1
						},
						{
						"name": "南墙电缆进出线_地面4号_无线水浸传感器_WSA16B",
						"online": 1
						}
					],
				"sensorTypeCountList":[
						{
							sensorType: "水浸传感器",
							count: 8
						},
						
					],
					"offlineCount": 0,
					"name": "10号汇聚节点",
					}
				],
				"name": "接入节点",
				}
			}, 500)
		},
    }
}
</script>

<style scoped>
#meshedNetwork {
    position: absolute;
    top: 0px;
	left: 0px;
    right: 0px;
    bottom: 0px;  
	background-color: #043e3d;
	
	display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}
</style>
