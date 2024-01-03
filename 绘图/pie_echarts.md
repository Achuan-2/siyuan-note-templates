{: id="20231218155204-oavecab"}

```echarts
{
  tooltip: {
    trigger: 'item'
  },
  legend: {
    top: '5%',
    left: 'center'
  },
    toolbox: {
            show: true,
	    orient:"vertical",

            feature: {
                dataView: {show:true},
                saveAsImage: {
                    excludeComponents :['toolbox'],
                    pixelRatio: 1
                }
	  
            },
	    top:'bottom'
        },
  series: [
    {
      name: 'Access From',
      type: 'pie',
      radius: ['40%', '70%'],
      avoidLabelOverlap: false,
      itemStyle: {
        borderRadius: 10,
        borderColor: '#fff',
        borderWidth: 2
      },
      label: {
        show: false,
        position: 'center'
      },
      emphasis: {
        label: {
          show: true,
          fontSize: 40,
          fontWeight: 'bold'
        }
      },
      labelLine: {
        show: false
      },
      data: [
        { value: 3, name: '吃饭' },
        { value: 8, name: '睡觉' },
        { value: 13, name: '打豆豆' },

      ]
    }
  ]
}
```
{: id="20231218155209-beaaxzl"}
