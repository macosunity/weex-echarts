<template>
  <div id="my_echarts" class="echart"></div>
</template>

<style>
  .echart {
    height: 400px;
    width: 700px;
  }
</style>


<script>
  import echarts from 'echarts'
  export default {
      mounted: function(){
          this.$nextTick(function(){
              this.draw('my_echarts');
          })
      },
    methods: {
      draw: function(id){ 
          var myChart = echarts.init(document.getElementById(id)); 
        
        var option = {
            tooltip: {
                show: true
            },
            legend: {
                data:['销量']
            },
            xAxis : [
                {
                    type : 'category',
                    data : ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子","男装"]
                }
            ],
            yAxis : [
                {
                    type : 'value'
                }
            ],
            series : [
                {
                    "name":"销量",
                    "type":"bar",
                    "data":[5, 20, 40, 10, 10, 20, 100]
                }
            ]
        };

        // 为echarts对象加载数据 
        myChart.setOption(option);
      }
    }
  }
</script>

