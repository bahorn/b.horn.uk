# 2D SDF tests

## Size Coding variation

<canvas id="c"><script>c=document.getElementById("c").getContext("2d"),t=p=10,o=t*t,m=Math,setInterval(e=>{for(t+=1/o,c.clearRect(0,0,150,150),x=0;x<o;x++)j=m.pow,s=m.sin,k=8*s(j(x%p/p-s(t),2)+j(x/p/p+s(t),2)),c.fillRect(x%p*p,x,p/2,p/2-k)},p);</script></canvas>

### Code

```html
<canvas id="c">
<script>
    c=document.getElementById("c").getContext("2d") // Obtain a canvas context
    t=p=10 /* start the time at 10, and the matrix size as 10 */
    o=t*t
    /* We use various math functions (sin and pow) a few times, so alias to save
    bytes*/
    m=Math
    j=m.pow
    s=m.sin
    /* Run this code every `p` microseconds */
    setInterval(e=>{
        t+=1/o /* */
        c.clearRect(0,0,150,150); /* Clear the screen */
        /* Loop through the 10*10 matrix */
        for(x=0;x<o;x++) {
            k=8*s(j(x%p/p-s(t),2)+j(x/p/p+s(t),2))
            /* Draw a rectange at the correct x position, with a slight offset
            to the y. The rectange varies it's height based on how intense the 
            point is */
            c.fillRect(x%p*p,x,p/2,p/2-k)
        }
    } , p);
</script>
</canvas>
```


### Minified

```html
<canvas id="c"><script>c=document.getElementById("c").getContext("2d"),t=p=10,o=t*t,m=Math,setInterval(e=>{for(t+=1/o,c.clearRect(0,0,150,150),x=0;x<o;x++)j=m.pow,s=m.sin,k=8*s(j(x%p/p-s(t),2)+j(x/p/p+s(t),2)),c.fillRect(x%p*p,x,p/2,p/2-k)},p);</script></canvas>
```
