# D3 Beginner 2

### 5. Scaling
How to use D3.js scales
```javascript
    const scale = d3.scaleLinear()
                        .domain([min,max])  //raw data
                        .range([min,max])   //visual channel
    scale(someValue) //returns translated value
```
    
To get min & max values from data:  
```javascript
    d3.min(data, d => d[someAttr])
    d3.max(data, d => d[someAttr])
    d3.extent(data, d => d[someAttr]) //returns [min,max]
```