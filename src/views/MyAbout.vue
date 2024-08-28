<template>
  <div ref="mychart" id="demoDiv"></div>
</template>

<script>
import * as echarts from 'echarts'
export default {
  mounted(){
    let myEcharts=echarts.init(this.$refs.mychart)
    myEcharts.setOption({
      title:{//echarts标题
        text:'主标题',
        link:'http://www.baidu.com',
        target:'self',//当前页打开链接
        backgroundColor:'pink',
        borderColor:'red',
        borderWidth:5,
        // x:'center',
        subtext:'副标题',
        textStyle:{
          color:'yellow',
          fontSize:30
        }
      },
      tooltip:{
        //触发类型
        trigger:'axis',
        //坐标轴指示器
        axisPointer:{
          type:'shadow'
        },
        // showContent:false
        //自定义的提示框信息
        // formatter(params){}
      },
      legend:{
        show:true,
        itemWidth:10,
        itemHight:10
      },
      xAxis:{
        data:['A','B',"C",'D']
      },
      yAxis:{

      },
      series:{
        name:'数据表',
        type:'bar',
        data:[120,130,140,150],
        markPoint:{
          data:[
            {
            type:'max',
            name:'最大值'
            },
            {
            type:'min',
            name:'最小值'
            }
          ]
        }
      }
    })
  }
}
</script>

<style>
#demoDiv{
  width: 500px;
  height: 500px;
  border: 1px solid red;
}
</style>