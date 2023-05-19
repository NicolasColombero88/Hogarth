# HOGARTH - FRONT END TEST 
## NICOLÁS COLOMBERO - Response Documentation
  
  
  
### Exercise 1: Add a new hero section.

For this exercise, I approached it from the scalability perspective. By using custom variables and the CSS calculation method, I established a dynamic control that facilitates the division based on the number of heroes to be presented.
  
Just adding the following module::

```html
<div class="multiHero">
  <figure class="multiHero-image"></figure>
  <div class="hero-copy">
    <h2>Space</h2>
    <h3>The final frontier.</h3>
   </div>
   <!-- LINK -->
   <a class="multiHero-link" href="http://space.com/"></a>
</div>
```

The hero section can be distributed *N* number of times.  
And with the dynamic controls (*customHero.css*), the distribution can be set per line in a responsive manner (Desktop, Tablet, Mobile).

```css
:root {
  --dividerDesk: 2;
  --dividerTab: 2;
  --dividerMob: 1;
  }
  ```
    
- - -
  
### Exercise 2: Fix the order of the timeline.

In this exercise, the goal was to achieve a mosaic effect with vertical adjustment and proper implementation of responsive design, using only CSS. It proved to be challenging. To be honest, it is the aspect I paid the most attention to. After struggling for a while with *flex* and *grid*, I gave up and took the path of creating two HTMLs to achieve the responsive vision. The visibility is determined by the classes .desktop and .mobile. (*customTimeline.css*)

```html
<section class="timeline">
        <div class="container">
            <div class="row">
                <div class="timeline-container col-12">
                    <h2 class='section-headline'>The Timeline</h2>
                </div>
            </div>
            <!-- DESKTOP VERSION START-->
            <div class="row desktop">
                ...
            </div>
            <!-- DESKTOP VERSION END-->

            <!-- MOBILE VERSION START-->
            <div class="row mobile">
                ...
            </div>
            <!-- MOBILE VERSION END-->
        </div>
    </section>
  ```
- - -
  
### Exercise 3: Support the gallery on older browsers.

In this exercise, I accepted the suggestion to maintain alignment using *float* or *flex*.  
To view one option or the other, it's a matter of commenting out the piece of code that we don't want to display (*legacyGrid.css*). These sections are clearly divided by descriptive comments.  
To solve this exercise I did not create any new class. I just gave new values to already existing classes from a new CSS sheet.  
It is worth clarifying that although the elements inside the grid continue to be called by media queries with grid attributes, these have no effect because in both cases the *display* of the container is no longer a grid, but a flex or block.

With *Flex* :

```css
/* OPTION 1 -- FLEX METHOD */

.gallery-grid {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}
```
With *Float* :

```css
/* OPTION 2 -- FLOAT METHOD */

.gallery-grid {
    display: block;
}
```
