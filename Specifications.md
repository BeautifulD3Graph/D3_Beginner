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

### 6. Group
How to use ```<g>``` tag   
![image](https://user-images.githubusercontent.com/45458274/147407593-eb216196-cdef-42e5-b0d3-fabbe730fbba.png)   

#### (1) Create ```<g>```elements for each movie store select in variable  
![image](https://user-images.githubusercontent.com/45458274/147407644-bebc5491-d34b-4831-a790-b44ddcfd31c4.png)   

![image](https://user-images.githubusercontent.com/45458274/147407798-adcd6208-eecf-48b9-a62b-921dcc061efa.png)

#### (2) Create a ```<text>``` element in each group. The child ```<text>``` inherit the parent data  

![image](https://user-images.githubusercontent.com/45458274/147407839-97a52bfb-a525-4b47-8b2e-8a01c4471058.png)   
![image](https://user-images.githubusercontent.com/45458274/147407849-e83b4944-d03a-4a5b-9919-a4761ce915f9.png)    

#### (3) For each ```<g>``` element, return array with length d.numpetals to create same number of ```<path>``` elements   
![image](https://user-images.githubusercontent.com/45458274/147408188-1ae9dd70-35fb-48ff-b4af-2e938fa3cc68.png)   
![image](https://user-images.githubusercontent.com/45458274/147408195-e871d157-cb20-4f27-a66d-7a8eb92c4e37.png)

