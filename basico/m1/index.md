---
title       : Análise de dados 
subtitle    : Módulo básico
author      : Marcio Nicolau
job         : Estatístico
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, quiz, shiny, interactive]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft, selfcontained}
ext_widgets : {rCharts: [libraries/nvd3, libraries/highcharts]}
github      : {user: marcionicolau, repo: courses}
assets:
  css: 
    - "http://fonts.googleapis.com/css?family=Open+Sans"
    - "http://fonts.googleapis.com/css?family=Oxygen"
--- &radio
<style>

body{
  font-family: 'Open Sans', sans-serif;
  font-size: 16px;
  line-height: 24px;
}

h1,h2,h3,h4 {
  font-family: 'Oxygen', sans-serif;
}

.container { width: 900px; }
</style>


## Question 1

What is 1 + 1?

1. 1
2. _2_
3. 3
4. 4

*** .hint

This is a hint

*** .explanation

This is an explanation

---
## Interactive Chart

<div id = 'chart1' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart1()
    });
    function drawchart1(){  
      var opts = {
 "dom": "chart1",
"width":    800,
"height":    400,
"x": "Hair",
"y": "Freq",
"group": "Eye",
"type": "multiBarChart",
"id": "chart1" 
},
        data = [
 {
 "Hair": "Black",
"Eye": "Brown",
"Sex": "Male",
"Freq":             32 
},
{
 "Hair": "Brown",
"Eye": "Brown",
"Sex": "Male",
"Freq":             53 
},
{
 "Hair": "Red",
"Eye": "Brown",
"Sex": "Male",
"Freq":             10 
},
{
 "Hair": "Blond",
"Eye": "Brown",
"Sex": "Male",
"Freq":              3 
},
{
 "Hair": "Black",
"Eye": "Blue",
"Sex": "Male",
"Freq":             11 
},
{
 "Hair": "Brown",
"Eye": "Blue",
"Sex": "Male",
"Freq":             50 
},
{
 "Hair": "Red",
"Eye": "Blue",
"Sex": "Male",
"Freq":             10 
},
{
 "Hair": "Blond",
"Eye": "Blue",
"Sex": "Male",
"Freq":             30 
},
{
 "Hair": "Black",
"Eye": "Hazel",
"Sex": "Male",
"Freq":             10 
},
{
 "Hair": "Brown",
"Eye": "Hazel",
"Sex": "Male",
"Freq":             25 
},
{
 "Hair": "Red",
"Eye": "Hazel",
"Sex": "Male",
"Freq":              7 
},
{
 "Hair": "Blond",
"Eye": "Hazel",
"Sex": "Male",
"Freq":              5 
},
{
 "Hair": "Black",
"Eye": "Green",
"Sex": "Male",
"Freq":              3 
},
{
 "Hair": "Brown",
"Eye": "Green",
"Sex": "Male",
"Freq":             15 
},
{
 "Hair": "Red",
"Eye": "Green",
"Sex": "Male",
"Freq":              7 
},
{
 "Hair": "Blond",
"Eye": "Green",
"Sex": "Male",
"Freq":              8 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .x(function(d) { return d[opts.x] })
          .y(function(d) { return d[opts.y] })
          .width(opts.width)
          .height(opts.height)
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>


--- &interactive
## Interactive Console

<textarea class='interactive' id='interactive{{slide.num}}' data-cell='{{slide.num}}' data-results='asis' style='display:none'>require(googleVis)
M1 <- gvisMotionChart(Fruits, idvar = 'Fruit', timevar = 'Year')
print(M1, tag = 'chart')</textarea>



---
## Interactive 2
<div class="row-fluid">
  <div class="span4">
    <form class="well">
      <label class="control-label" for="sex">Choose Sex</label>
      <select id="sex">
        <option selected="selected" value="Male">Male</option>
        <option value="Female">Female</option>
      </select>
      <label class="control-label" for="type">Choose Type</label>
      <select id="type">
        <option selected="selected" value="multiBarChart">multiBarChart</option>
        <option value="multiBarHorizontalChart">multiBarHorizontalChart</option>
      </select>
    </form>
  </div>
  <div class="span8">
    <div class="shiny-html-output nvd3 rChart" id="nvd3plot"></div>
  </div>
</div>


---
## Interactive 3
<iframe src=assets/fig/unnamed-chunk-4.html seamless></iframe>


--- &twocols
### Two Column Layout   
This slide has two columns
    
*** =left w:40%
    
- point 1
- point 2
- point 3
    
*** =right w:60%

- point 1
- point 2
- point 3

--- &twocols

### Two Columns

This slide has two columns

*** =left w:60%

- point a
- point b
- point c

*** =right w:40%

- point a
- point b
- point c

---

## Another attempt to add rCharts


```r
haireye = as.data.frame(HairEyeColor)
n1 <- nPlot(Freq ~ Hair, group = "Eye", type = "multiBarChart", data = subset(haireye, 
    Sex == "Male"))
n1$addParams(width = 500, height = 500)
n1$addControls("group", "Eye", names(haireye))
n1$addControls("type", "multiBarChart", c("multiBarChart", "multiBarHorizontalChart"))
n1$save("rp2.html", cdn = TRUE)
```

<iframe src="rp2.html" width=1200 height=600> </iframe>

