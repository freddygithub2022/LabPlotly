---
title: "Lab Plotly"
author: "Freddy Espinoza"
date: '2022-06-27'
output: html_document
---

# Graphics lab with Plotly.


```{r}
library(ggplot2)
library(plotly)

use_cpu <- rnorm(100, mean = 75, sd = 7)
use_ram <- rnorm(100, mean = 55, sd = 3)

x <- c(1:300)

data <- data.frame(x, use_cpu, use_ram)

fig <- plot_ly(data, x = ~x, y = ~use_cpu, name = 'Use CPU', type = 'scatter', mode = 'lines') 
fig <- fig %>% add_trace(y = ~use_ram, name = 'Use RAM', mode = 'lines+markers') 

fig <- fig %>% layout(title ='Computing Consumption', xaxis = list(title = 'Day of Year'), yaxis = list(title = 'Computing Resources (%)'))

fig
```

# View html result

https://rawcdn.githack.com/freddygithub2022/LabPlotly/7f9c40552b684fc8a334e7aa23d58a6f690988aa/MyLabPlotly.html
