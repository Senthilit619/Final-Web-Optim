This readme file includes the steps that were taken to successfully optimize the pages.
The first section guides through the steps for increasing the PageSpeed score for index.html
The second section involves the steps for rendering a smooth pizzeria.html page

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

             SECTION-1

1. In the index.html page, the main cause for slow rendering is the css and javascript files which block the rendering process.
2. So, the first step is to make those files not to block the rendering. For that, the css is inlined so that the browser doesn't wait for the style.css file and also the critical resources is reduced.
3. Next, the scripts in the index.html is moved just above the </body> tag. This is to make sure that the rendering is affected by those scripts which might do some calculations in it. 
4. Also, the scripts are added an async attribute which will indicate the browser that these scripts should be in a separate line of processing and not affect the rendering.
5. Next, the pizzeria.jpg image which is 2.2MB sized file is compressed to a small 6KB file so that it doesnt comsume the bandwidth. Because, it is just a part of the webpage and is not that significant.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

			SECTION-2

1. In this section, the steps involve the optimization of the UI for the pizzeria.html
2. First, the slider to resize the pizza images is changed. The determinedx function is just a small calculation of the size of th pizza which isnt a great concern for the user. So, the size is made static for the three available sizes and the function determinedx function is removed. Also the loop has some redundant code to select the elements using the queryselector. That is changed to using the DOM selector and moved it outside the loop whcih is sufficient.
3. Next, the updatePosition function is optimized using the same technique. The calculation is moved outside the loop and doen only once.
4. Another major one to be optimized is the number of pizza images to be rendered in the background. By default, it is looped 200 times to create 200 pizzas. But, on seeing the page, the number if pizzas is calculated using rows and cols. The rows is calculated using the height of the browser.
5. Next the pizzas which are created using the mover class is added a css effect "will-change:transform" which will promote the pizzas to an individual layer and thus making it to render as a separate layer. This will reduce area being rendered in the page when scrolled.
6. The style.left in the updatePosition can be changed to style.transform since the transform only affects the compositing and not the painting and rendering.
7. In the style.css, the backface-visibility:hidden property is added to improve the rendering.
8. In the whole script, the query selector is replaced with the DOM selector.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
