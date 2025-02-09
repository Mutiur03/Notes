https://youtu.be/xI9G0Zh5DVA?si=jbc-gPInJkrR7u91

```css
.container{
    display: grid;
    grid-template-rows: repeat(5,50px);
    grid-template-columns: repeat(3,1fr);
}

.item-6{
    background-color: aqua;
    /* grid-column: 2/4; /* /(this position+total col)**/
    /*grid-row: 4/6; */
    grid-area: 4 / 2 / 6 / 4;
    /*alternative of grid row and col*/
    /* row begin/col begin/row end/col end*/
    z-index: 1;
}
.item-5{
    background-color: aquamarine;
    grid-row: 4;
    grid-column: 2;
    z-index: 10;
}
```

![[Pasted image 20250208004134.png]]


For responsive design 

```css
grid-template-rows: repeat(auto-fill,50px);
grid-template-columns: repeat(auto-fill,100px);
```