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

#### (1) Draw Bar Chart
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
![image](https://user-images.githubusercontent.com/45458274/144745726-71e42a1d-57a1-4498-a541-78d92d0a547b.png)


#### misson!
![image](https://user-images.githubusercontent.com/45458274/144745893-4ae8efa2-7b2b-4ed8-8e25-07f97ea3cfac.png)

<details>
  <summary>Answer</summary>
    <div markdown="1">
     
     d3.select(svg).selectAll('rect')  
    .data(barData)  
    // calculate x-position based on its index   
    .attr('x', (d, i) => i * rectWidth)   
    .attr('y', (d,i) => 100 - d)    //add   
    // set height based on the bound datum   
    .attr('height', d => d)     
    // rest of attributes are constant values   
    .attr('width', rectWidth)   
    .attr('stroke-width', 2)    
    .attr('stroke', 'red')        //modified  
    .attr('fill', 'skyblue')      //modified   
     
   </div>
</details>

#### summary
![image](https://user-images.githubusercontent.com/45458274/144746208-194f6d2c-2326-4e46-8793-bc3eb65be020.png)

#### (2) exercise time!

![image](https://user-images.githubusercontent.com/45458274/144746607-3e57ec97-5414-41a9-b69f-bbdb054a0579.png)

code
```javascript
const svg = html`
    <svg width=500 height=100 style='border: 1px dashed'>
      <path d='${petalPath}' transform='translate(50, 0)' />
      <path d='${petalPath}' transform='translate(150, 0)' />
      <path d='${petalPath}' transform='translate(250, 0)' />
      <path d='${petalPath}' transform='translate(350, 0)' />
      <path d='${petalPath}' transform='translate(450, 0)' />
    </svg>
  `
  
  // YOUR CODE HERE 
  const path = d3.select(svg).selectAll('path').data(movies)
    .attr('fill',d => colors[d.genres[0]] || colors.Other)
  // .attr('fill',d => console.log(d)) 콘솔을 통해 어떤 데이터가 들어갔는지 확인하자
  // console.log(path) 콘솔을 통해 어떤 데이터가 들어갔는지 확인하자
 
  return svg
```

### 4. Approaching the DOM.
Let's learn about
```javascript
d3.select(svg).selectAll('rect')
  .data(data).enter().append('rect')
```
<img width="727" alt="스크린샷 2021-12-05 오후 9 58 18" src="https://user-images.githubusercontent.com/45458274/144747620-555de087-7589-4be1-bf08-244ca3b57aff.png"> 
 
![image](https://user-images.githubusercontent.com/45458274/144747469-ae4be610-13f6-4562-860c-e34e28e046c0.png)  


Source.
1. https://observablehq.com/@sxywu/introduction-to-svg-and-d3-js
