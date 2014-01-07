---
title       : Introdução
subtitle    : Como aprender com os dados
author      : Marcio Nicolau
job         : Estatístico
framework   : revealjs        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax, bootstrap, quiz, interactive]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
ext_widgets : {rCharts: [libraries/nvd3, libraries/highcharts]}
github      : {user: marcionicolau, repo: courses}
twitter:
  text: "Slidify with impress.js!"
revealjs:
  theme: sky # c("sky", "beige", "simple", "serif", "night", "default", "solarized", "moon")
  transition: concave # c("cube", "page", "concave", "zoom", "linear", "fade", "none", "default")
  center: "true"
url: {lib: "."}
bootstrap:
  theme: amelia
assets:
  css: 
    - "http://fonts.googleapis.com/css?family=Open+Sans"
    - "http://fonts.googleapis.com/css?family=Oxygen"
    - "http://fonts.googleapis.com/css?family=Lato:400,700,400italic,700italic"
    - "http://fonts.googleapis.com/css?family=Alfa+Slab+One|Raleway:100"
    - "./assets/css/main.css"
--- 

<style>

html, body {	
	font-family: Raleway, 'Arial Narrow' , sans-serif;
	font-size: 32px;
	font-weight: 400;
	letter-spacing: -0.02em;
	
	color: #222;
}

h1, 
#reveal h2, 
#reveal h3, 
#reveal h4 {
  margin: 0 0 20px 0;
	
	color: #333;
	
	font-family: 'Alfa Slab One', sans-serif;
	line-height: 0.9em;
	letter-spacing: -0.02em;
	
	text-transform: uppercase;
	text-shadow: 0px 0px 6px rgba(0,0,0,0.2);
}
</style>

# Introdução
### Como aprender com os dados

<small> [Marcio Nicolau](http://www.marcionicolau.mat.br) / Estatístico </small>

<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>

*** =pnotes

Some notes on the first slide

---

## Heads Up

reveal.js is a framework for easily creating beautiful presentations using HTML. You'll need a browser with support for CSS 3D transforms to see it in its full glory.

---

## Intergalactic Interconnections

You can link between slides internally, [like this](#/2/3).

---

## Fragmented Views

Hit the next arrow...

.fragment ... to step through ...

> - any type
> - of view
> - __fragments__

---

## Take a Moment

Press b or period on your keyboard to enter the 'paused' mode. This mode is helpful when you want to take distracting slides off the screen during a presentation.


---

## Incremental Paragraphs

.fragment This is paragraph 1 and should appear on first click.

.fragment This is paragraph 2 and should appear on second click.

.small [Back to the Beginning](#/0)


---

## Title

This is a slide

- point 1
- point 2
- point 3

---

## Incremental Reveal

These points should be animated

> - Point 1
> - .highlight-red Point 2
> - .grow Point 3

<script>
$('ul.incremental li').addClass('fragment')
</script>

---

## Code with slide


```r
library(ggplot2)
qplot(wt, mpg, data = mtcars)
```

![plot of chunk unnamed-chunk-1](assets/fig/unnamed-chunk-1.png) 


--- &vertical ds:soothe

## Vertical Slides

The next set of slides will be vertical slides.

***

## Slide 1

This is slide 1

***

## Slide 2

<iframe src='http://www.statdistributions.com' width = '960px' height = '600px'></iframe>

