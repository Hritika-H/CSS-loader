# CSS-loader
A Loader in CSS

![image](https://user-images.githubusercontent.com/32535755/205431816-44d6966c-d345-4d35-8d25-20674d8420a7.png)


A throbber, also known as a loading icon or a loader, is an animated graphical control element used to show that a computer program is performing an action in the background (such as downloading content, conducting intensive calculations or communicating with an external device). 

The spinning bars is one of the more common loader patterns.
 
For this loader create one element for each bar wrapped inside a parent element (for nine total elements), then play with opacity and transform to get the spinning effect.
 
**CSS Explanation:**

```width: 150px; ```

*one value for controlling the overall size*

```aspect-ratio: 1; ```

*defines the dimension of the element. Here the element stays square no matter what.*

```display: grid; ```

*This allows us to rely on the grid’s default stretch alignment to make the pseudo-element cover the whole area of its parent; thus there’s no need to specify a dimension on it*

```background: linear-gradient(#17177c 0 0) 50%/34% 8% space no-repeat;```
    
*Our gradient is defined with one color and two color stops. The result is a solid color with no fading or transitions. The size is equal to 34% wide and 8% tall. 
It’s also placed in the center (50%). center/width heigth
The trick is the use of the keyword value space — this duplicates the gradient, giving us two total bars.*

```
background: linear-gradient(#8609f4 0 0) 50%/34% 8% space no-repeat,
            linear-gradient(#8609f4 0 0) 50%/8% 34% no-repeat space; 
```

*Creating css variable to avoid repetition in code. 
Variable name starts with -- 
Value that can be used in other declarations using the var() function.*

```
--lg: linear-gradient(#9629f6 0 0) 50%;

background: var(--lg)/34% 8% space no-repeat,
                var(--lg)/8% 34% no-repeat space;
```

*In CSS, ::before creates a pseudo-element that is the first child of the selected element. 
It is often used to add cosmetic content to an element with the content property.*

*The mask CSS shorthand property hides an element (partially or fully) by masking or clipping the image at specific points.
What we’re trying to do is create the impression that there is one bar that leaves a trail of fading bars behind it as it travels a circular path. 
What we need now is to play with the transparency of our bars to make that trail, which we are going to do with CSS mask combined with a conic-gradient*
```
-webkit-mask: conic-gradient(from 22deg, #0003,#000);
    mask: conic-gradient(from 22deg,#0003,#000);
```
*The term 'webkit' is used in the CSS syntax for rendering content in Safari and Chrome browsers. 
Webkit code may need to be added in CSS to ensure it renders correctly on Chrome and Safari due to the lack of cross-compatibility.* 

```animation: load 3s steps(8) infinite; ```

*To create a CSS animation sequence, you style the element you want to animate with the animation property or its sub-properties. 
This lets you configure the timing, duration, and other details of how the animation sequence should progress.  
The @keyframes CSS at-rule controls the intermediate steps in a CSS animation sequence by defining styles for keyframes (or waypoints) along the animation sequence.
to and from specify the start or end states of the animation*

```
@keyframes load {
    from {transform: rotate(0turn)}
    to {transform: rotate(1turn)}
}
```
