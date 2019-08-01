<template>
  <div id="app">
    <div id="main" style="width: 100%;height:800px;"></div>
  </div>
</template>

<script>
/* eslint-disable */
import echarts from 'echarts'
import 'echarts/map/js/china.js';
import china from '../static/map/china.json'
import anhui from '../static/map/province/anhui.json'


export default {
  name: 'App',
  data () {
    return {
      myChart: undefined,
      option: {
	      backgroundColor: '#000',
        title : {
            text: 'Echarts3 中国地图下钻至县级',
            subtext: '三级下钻',
            link:'http://www.ldsun.com',
            left: 'center',
            textStyle:{
                color: '#fff',
                fontSize:16,
                fontWeight:'normal',
                fontFamily:"Microsoft YaHei"
            },
            subtextStyle:{
              color: '#ccc',
                fontSize:13,
                fontWeight:'normal',
                fontFamily:"Microsoft YaHei"
            }
        },
        tooltip: {
            trigger: 'item',
            formatter: '{b}'
        },
        toolbox: {
            show: true,
            orient: 'vertical',
            left: 'right',
            top: 'center',
            feature: {
                dataView: {readOnly: false},
                restore: {},
                saveAsImage: {}
            },
            iconStyle:{
              normal:{
                color:'#fff'
              }
            }
        },
        animationDuration:1000,
        animationEasing:'cubicOut',
        animationDurationUpdate:1000    
      }
    }
  },
  mounted(){
    var vm = this;
    this.myChart = echarts.init(document.getElementById('main'));
    let d = [];
    for( var i=0;i<china.features.length;i++ ){
      d.push({
        name:china.features[i].properties.name
      })
    }
    echarts.registerMap('china', china);
    this.renderMap('china',d);
    console.log(this)
    this.myChart.on('click', function (params) {
      console.log( params.name );
      let that = this
      echarts.registerMap( '安徽', anhui);
			let d = [];
			for( var i=0;i<anhui.features.length;i++ ){
				d.push({
					name:anhui.features[i].properties.name
				})
      }
      console.log(vm)
			vm.renderMap('安徽',d);
    })
    // let option = {
    //   series: [
    //     {
    //       name: "china",
    //       type: 'map',
    //       mapType: "china",
    //       label: {
    //         normal: {
    //           show: true,//显示省份标签
    //         },
    //         emphasis: {
    //           show: true,//对应的鼠标悬浮效果
    //         }
    //       },
    //     }
    //   ]
    // };
    // myChart.setOption(option);
    // myChart.on('click', function (params) {
    // console.log( params.name );
    // })
  },
  methods: {
    renderMap(map,data){
    this.option.title.subtext = map;
    this.option.series = [ 
      {
        name: map,
        type: 'map',
        mapType: map,
        roam: false,
        nameMap:{
          'china':'中国'
        },
        label: {
          normal:{
            show:true,
            textStyle:{
              color:'#999',
              fontSize:13
            }  
          },
          emphasis: {
              show: true,
              textStyle:{
                color:'#fff',
                fontSize:13
					}
        }
      },
      itemStyle: {
        normal: {
          areaColor: '#323c48',
          borderColor: 'dodgerblue'
        },
        emphasis: {
          areaColor: 'darkorange'
        }
      },
      data:data
      }	
    ];
    //渲染地图
    this.myChart.setOption(this.option);
  }

  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
* {
  margin: 0;
  padding: 0;
}
body {
  font-family: Exo,'-apple-system','Open Sans',HelveticaNeue-Light,'Helvetica Neue Light','Helvetica Neue','Hiragino Sans GB','Microsoft YaHei',Helvetica,Arial,sans-serif;
  color: #333333;
}
</style>
