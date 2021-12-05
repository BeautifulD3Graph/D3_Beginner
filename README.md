# D3 Beginner

## SVG 

### SVG viewport & Coordinate system  
![image](https://user-images.githubusercontent.com/45458274/144718143-d88f5eb3-75b5-46bb-b7f3-a06c74946d91.png)


SVG elements!  
![image](https://user-images.githubusercontent.com/45458274/144718175-48073fcf-d7a6-43cb-b204-282f4677c3ef.png)  
![image](https://user-images.githubusercontent.com/45458274/144730312-d28f6479-b711-48e3-b25d-d4c3cc975884.png)  
![image](https://user-images.githubusercontent.com/45458274/144730307-bf5b9a43-9687-4484-8494-1c2ebcaa513e.png)


exercise time!  
![image](https://user-images.githubusercontent.com/45458274/144718872-6f3404f2-bad4-417d-a203-0414240f9ec9.png)
![image](https://user-images.githubusercontent.com/45458274/144718985-f3f13ec6-08c5-43c1-96f1-c0f26d517819.png)
![image](https://user-images.githubusercontent.com/45458274/144718992-3633376d-b1af-40dc-9f9d-bd2ff70e1d9b.png)  
![image](https://user-images.githubusercontent.com/45458274/144730084-28dcb100-1bf6-4051-afa4-d2c76a2e0576.png)  

## D3 

### 1. Element Selections module

Let's learn about
```javascript
d3.select() and d3.selectAll().  
```
![image](https://user-images.githubusercontent.com/45458274/144730645-357c9587-c030-4db6-8a98-6f665a9458ec.png).  
![image](https://user-images.githubusercontent.com/45458274/144730653-58f4f595-ea93-43de-8fcb-7b160896e1d0.png)   

result.  
![image](https://user-images.githubusercontent.com/45458274/144730657-97302ac1-ce56-44e0-a077-72951496f6f2.png)  

### 2. Data Binding

Let's learn about
```javascript 
selection.datum() and selection.data(). 
```

setting.   
```javascript
const barData = [45, 67, 96, 84, 41]     

const el = html`<svg>   
                      <rect/>   
                      <rect/>   
                      <rect/>   
                      <rect/>   
                      <rect/>   
                    </svg>`   
                    
const svg = d3.select(el)   
```


#### (1) select & datum
```javascript
return svg.select('rect').datum(barData)
```  
![image](https://user-images.githubusercontent.com/45458274/144730886-b6deeb43-bef0-42eb-9526-6e6d9ca05a42.png)


#### (2) selectAll & datum
```javascript
return svg.selectAll('rect').datum(barData)
```  
![image](https://user-images.githubusercontent.com/45458274/144730901-6ddddfae-f3c9-43d7-8164-66c277e5560e.png)

#### (3) selectAll & data
```javascript
return svg.selectAll('rect').data(barData)
```  
![image](https://user-images.githubusercontent.com/45458274/144730918-3ea05e55-1f3f-4bf3-8b2e-36dd58b58d12.png)   

#### summary
![image](https://user-images.githubusercontent.com/45458274/144731085-a127ed89-eaf9-4590-a044-9af9edba624d.png)


### 3. Document Styling
Let's learn about
```javascript 
  selection.attr() and selection.style()
```
setting  
```javascript
 const barData = [45, 67, 96, 84, 41]
 const svg = html`
    <svg width=${rectWidth * barData.length} height=100 style='border: 1px dashed'>
      <rect />
      <rect />
      <rect />
      <rect />
      <rect />
    </rect>
  `
  // console.log(barData)
  d3.select(svg).selectAll('rect')
    .data(barData)
    // calculate x-position based on its index(x축 시작지점 설정)
    .attr('x', (d, i) => i * rectWidth)
    .attr('y', (d,i) => 100 - d)
    // set height based on the bound datum(높이 설정)
    .attr('height', d => d)
    // rest of attributes are constant values(넓이 설정)
    .attr('width', rectWidth)
    //테두리 두께 설정
    .attr('stroke-width', 2)
    //테두리 유형 길이, 사이 넓이 설정
    .attr('stroke-dasharray', '5 5')
    //테두리 색상 설정
    .attr('stroke', 'black')
    //차트 색 채우기(background color)느낌
    .attr('fill', 'skyblue')
  
  return svg
```

result   


resources
1. https://observablehq.com/@sxywu/introduction-to-svg-and-d3-js
2. https://bl.ocks.org/
