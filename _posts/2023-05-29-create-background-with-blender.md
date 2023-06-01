---
layout: post
title:  "Create a background wallpaper with Blender"
date:   2023-05-29 10:11:00 +020
description: > 
 Ever wanted to create your own nice looking background wallpaper? In this short blog post you can learn how, 
 using a greate free tool called Blender.
---

{{ page.description }}  
Even so Blender is a complex tool, with which you can do many things like creating models for images, games, videos, etc and animate them, it is still easy to use to create simple things like a wallpaper for instance. 

## Get started
In this tutorial I asume that you already have installed Blender. If this is not the case, you can follow this quick tutorial [here](https://docs.blender.org/manual/de/dev/getting_started/installing/index.html).  

With Blender installed now, we can dive right into it.  


## Create the foreground

For the foreground part I used the tutorial of [Blender Made Easy - How to Make a cool Blender Wallpaper](https://www.youtube.com/watch?v=Z_kAzpmgNN8&ab_channel=BlenderMadeEasy). You can follow the tutorial on youtube or here.  

The first thing we have to do is to create our hexagon. For this we add a cylinder `Shift + A -> Mesh -> Cylinder`and change the number of verticies to 6.  

<div class="image-with-description-right ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/add_cylinder.png" height="200">
    <p>
        This can be done using the Add Object window at the bottom left corner. Now ther should open a window where you can change the number of <code class="language-plaintext highlight-rouge">Verticies</code>.
    </p>
</div>
<div class="image-with-description-left ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/add_array_modifier.png" height="300">
    <p>
        Next thing we want to do is create multiple instances of this object. For this we select our object and apply the array modifier in the <code class="language-plaintext highlight-rouge">Modifier Properties</code> section. At the toolbar on the right there is the open-end-wrench 🔧 symbol click it and use the <code class="language-plaintext highlight-rouge">Add Modifier</code> button to add an array modifier.
        <br><br>
        In the modifier settings set the count to 20 to create multiple hexagons. Now set the <code class="language-plaintext highlight-rouge">Relative Offset</code> to 1.01 to create little gaps between each hexagon.
    </p>
</div>

You should by now have a row of multiple hexagones lined up next to each other. Click the `Apply` button in the array modifier panel to apply the array modifier. Now our object is made of a row with several hexagons.

![hexagon row]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/hexagon_row.png){: style="height:400px; display:block; margin-left:auto; margin-right:auto"}

Again we want to duplicate this row. To do that select the row and press `Shift + D` . Now position the duplicated row on top of the other row but with a little offset to the right. So the corners of the hexagons of the first row go between the corners of the second. You can adjust the distance between the two rows by selecting the second row and select the `Object Properties` panel which has the little orange square symbol. There you can adjust the X and Y location so that the distances between the hexagons are rougly the same.  

![object properties]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/object_properties.png){: height="300" style="margin-right: 30px;"}
![hexagon distance]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/hexagon_distance.png){: height="300" style="margin-right: 30px;"}
![hexagon distance]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/hexagon_rows.png){: height="200"}

At the top right corner is you project tree. There you should see know two objects called `Cylinder` and `Cylinder.001`. Each one represents one row. To join both of these rows to one single object select both of them and press `Ctrl + j`. The project tree should now contain only `Cylinder.001` out of the two.
Now we copy these two rows again by selecting everything and pressing `Shift + D` again. Every time you copy put the resulting rows on top of the previous. Like this we can create multiple rows of hexagones. In the end there should now be a rectangle field with many hexagons.  


<div class="image-with-description-right ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/camera_positioning.png" height="300">
    <p>
        The next thing we want to do is to center the camera. You should first make sure that you looking top down onto the rows. The best way to do that is to click on the little blue Z of the axis in the top right corner. Then press <code class="language-plaintext highlight-rouge">Ctrl + Alt + Num_0</code> to center the camera. The camera should cover rougly the whole field. You can move the camera by selecting the camera view, pressing <code class="language-plaintext highlight-rouge">G</code> and moving your mouse to adjust the position to zoom in or out press <code class="language-plaintext highlight-rouge">z</code>.  
    </p>
</div>



<div class="image-with-description-left ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/edit_mode.png" height="200">
    <p>
        After that select all rows which should be just a left click somwhere in the hexagon rectangle. Switch to <code class="language-plaintext highlight-rouge">Edit Mode</code> by clicking on the drop dow menu at the top left corner. Now press <code class="language-plaintext highlight-rouge">p</code> and select <code class="language-plaintext highlight-rouge">By loose parts</code>. This can take a view seconds. Switch back to  <code class="language-plaintext highlight-rouge">Object Mode</code>. You should now have all the hexagons as single objects in the project tree. The select all the hexagons do a right click and select  <code class="language-plaintext highlight-rouge">Set Origin -> Origin to Geometrie</code> . This might also take some time. 
    </p>
</div>

To finish the foreground we select one hexagone and press `o` to turn on `Proportional editing object mode`. Click on the `Move` button on the left toolbar and click on the blue arrow wich appears now close to the selected hexagon. With this arrow we can now move the hexagon a little bit upwards and in the bottom left corner there should now pop up a window saying `Move`.


<div class="image-with-description-right ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/move.png" height="200">
    <p>
        For the <code class="language-plaintext highlight-rouge">Proportional Falloff</code> select <code class="language-plaintext highlight-rouge">Random</code> and change the number for <code class="language-plaintext highlight-rouge">Proportional Size</code> to something like 8.0. After that again select on of the hexagons and move it upwards. The sorounding hexagons should now move as well. You can move several of the hexagons depending on what you find appealing.
    </p>
</div>

The whole thing should by now look similar to this.

![hexagon distance]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/after_propotional_editing_1.png){: height="300" style="margin-right: 30px;"}
![hexagon distance]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/after_propotional_editing_2.png){: height="300"}

Now we have to do some configurations for the rendering. I changed the lamp to `Sun` and reduced the `Strengh` a little by clicking at the lamp object and selecting the  lightbulb 💡 from the toolbar to the right bottom corner, which is the `Object Data Properties` panel. The sun mode lets the lamp act like the sun on earth would do. The light rays go in on direction. You can adjust the position of your sun and the direction of the rays to your liking. I choose the top right corner. 

<div class="image-with-description-left ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/rendering.png" height="100">
    <p>
        To see the outcome of your adjustments switch the <code class="language-plaintext highlight-rouge">Viewport Shading</code> to <code class="language-plaintext highlight-rouge">Rendered</code>. This is done by clicking at the outer right circle in the top right toolbar. This switches to the realtime render mode. Now you should be able to see the shadows your light is producing. 
    </p>
</div>

<div class="image-with-description-right ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/rendering_mode.png" height="100">
    <p>
        While this might already look quite good, we will change the render mode to <code class="language-plaintext highlight-rouge">Cycles</code>. Since this mode produces smoother shadows. Click at the <code class="language-plaintext highlight-rouge">Render Properties</code> which is the camera symbol in the toolbar on the right. In the panel you can change in the <code class="language-plaintext highlight-rouge">Render Engine</code> drop down menu to <code class="language-plaintext highlight-rouge">Cycles</code>. No the rendering always takes a little bit and you can follow the process as the image sharpens more and more.
    </p>
</div>

<div class="image-with-description-left ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/material.png" height="300">
    <p>
        The last thing we have to do for the foreground is to add a material to the hexagons. We do that by selecting one hexagon switching to the <code class="language-plaintext highlight-rouge">Material Properties</code> which should have a red circle as an icon. In the panel we add a new material by hitting the <code class="language-plaintext highlight-rouge">New</code> Button. In the panel do the same configurations as I did in the image. Basically we set the <code class="language-plaintext highlight-rouge">Surface</code> to <code class="language-plaintext highlight-rouge">Mix Shader</code> and add the <code class="language-plaintext highlight-rouge">Defuse BSDF</code> and <code class="language-plaintext highlight-rouge">Glossy BSDF</code> shader. To apply the material to all the hexagons select all hexagons, press <code class="language-plaintext highlight-rouge">Shift</code> and left click the hexagon with the material applied and press <code class="language-plaintext highlight-rouge">Ctrl + L</code> then select <code class="language-plaintext highlight-rouge">Materials</code> in the pop up menu. Now all the hexagons should have this material. You can check that by clicking on another hexagon and check the <code class="language-plaintext highlight-rouge">Material Properties</code> where there should be the earlier created material. <br>
        Now let's render an image of the whole foreground by clicking on the <code class="language-plaintext highlight-rouge">Render</code> at the top menu next to the <code class="language-plaintext highlight-rouge">File</code> and <code class="language-plaintext highlight-rouge">Edit</code> button. 
    </p>
</div>

This should open a new window where you can follow the render process. If the image produces is noisy you can increase the `Samples` in the `Render Properties` panel which should right now have a default of 128. The result should now look similar to this.

![rendered image]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/rendered_image.png){: style="display:block; margin-left:auto; margin-right:auto; height:500px"}

Great! You have finished the foreground so far. Take a second a pat yourself on the back.   
---

## The background

The foreground itself already looks quite good. We could stop here and use this as our new wallpaper. But I want something a little darker. To have a better contrast. Let us continue with the background to get a little bit more color.