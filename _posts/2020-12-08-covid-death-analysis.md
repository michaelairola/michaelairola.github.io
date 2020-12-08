---
title: 
tags: data-analysis data covid death life-expectancy 
chart: true
---

<!-- We all know the classic hypothetical:  -->

```chart
{
  "type": "bar",
  "data": {
    "labels": ["0-9", "10-19", "20-29", "30-39", "40-49", "50-59", "60-69", "70-79", "80+"],
    "datasets": [
      { 
        "label": "Death Count",
        "data": [ 71, 134, 847, 2259, 5384, 13942, 29887, 45325, 85182 ],
        "backgroundColor": "#FF6384"
      }
    ]
  },
  "options": {
    "legend": { "display": false },
    "title": {
        "display": true,
        "text": "Covid Deaths, U.S."
    }
  }
}
```
```chart
{
  "type": "bar",
  "data": {
    "labels": ["0-9", "10-19", "20-29", "30-39", "40-49", "50-59", "60-69", "70-79", "80+"],
    "datasets": [
      { 
        "label": "Life Years Lost",
        "data": [ 8209, 13451, 75822.9, 169952.1, 322639.2, 623627, 920959.2, 841076.5, 752032.5 ] ,
        "backgroundColor": "#FF6384"
      }
    ]
  },
  "options": {
    "legend": { "display": false },
    "title": {
        "display": true,
        "text": "Life-Years lost from Covid, U.S."
    }
  }
}
```
```chart
{
  "type": "bar",
  "data": {
    "labels": [ "0-24", "25-44", "45-64", "65-74", "75-84", "85+" ],
    "datasets": [
      { 
        "label": "Death Count over Average Per Year U.S.",
        "data": [ -14270.4, 33421.4, 6786.2, 93338.2, 82735.8, -1762.2 ],
        "backgroundColor": "#FF6384"
      }
    ]
  },
  "options": {
    "legend": { "display": false },
    "title": {
        "display": true,
        "text": "Predicted Excess Deaths in 2020, U.S."
    }
  }
}
```
```chart
{
  "type": "bar",
  "data": {
    "labels": [ "0-24", "25-44", "45-64", "65-74", "75-84", "85+" ],
    "datasets": [
      { 
        "label": "Life Years over Average Per Year U.S.",
        "data": [ -943273.5, 1493101.045, 181870.16, 1404739.9, 707391.09, -8987.22 ],
        "backgroundColor": "#FF6384"
      }
    ]
  },
  "options": {
    "legend": { "display": false },
    "title": {
        "display": true,
        "text": "Predicted Life-Years Lost excess in 2020, U.S."
    }
  }
}
```