---
layout: post
title:  "Create a wallpaper with Blender"
date:   2023-05-29 10:11:00 +020
description: > 
 Have you ever wanted to create your own beautiful wallpaper? This short blog post will show you how, 
 using a great free tool called Blender.

image_name: foreground_rendered_bloom.png
image_info: "Foreground rendered with bloom"
---

{{ page.description }}  
Even though Blender is a complex tool that allows you to do many things like create and animate models for pictures, games, videos, etc., it is still easy to use to create simple things like a wallpaper.

## Get started
In this tutorial I assume you already have Blender installed. If this is not the case, you can follow this short tutorial [here](https://docs.blender.org/manual/de/dev/getting_started/installing/index.html).  

With Blender now installed, we can dive right in.  


## Create the foreground

For the foreground part I used the tutorial from [Blender Made Easy - How to Make a cool Blender Wallpaper](https://www.youtube.com/watch?v=Z_kAzpmgNN8&ab_channel=BlenderMadeEasy). You can follow the tutorial on Youtube or here.  

The first thing we need to do is to create a hexagon. For this we add a cylinder `Shift + A -> Mesh -> Cylinder` and change the number of vertices to 6.  

<div class="image-with-description-right ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/add_cylinder.png" style="max-height: 200px">
    <p>
        This can be done using the Add Object window at the bottom left corner. Now a window should open where you can change the number of <code class="language-plaintext highlight-rouge">Vertices</code>.
    </p>
</div>
<div class="image-with-description-left ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/add_array_modifier.png" style="max-height: 300px">
    <p>
        Next thing we want to do is create multiple instances of this object. For this we select our object and apply the array modifier in the <code class="language-plaintext highlight-rouge">Modifier Properties</code> section. In the toolbar on the right there is the open-end-wrench 🔧 symbol. Select it and use the <code class="language-plaintext highlight-rouge">Add Modifier</code> button to add an array modifier.
        <br><br>
        In the modifier settings set the count to 20 to create multiple hexagons. Now set the <code class="language-plaintext highlight-rouge">Relative Offset</code> to 1.01 to create little gaps between each hexagon.
    </p>
</div>

You should by now have a row of multiple hexagons lined up next to each other. Click the `Apply` button in the array modifier panel to apply the array modifier. Our object now consists of a row of hexagons.

![hexagon row]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/hexagon_row.png){: style="max-height:400px; display:block; margin-left:auto; margin-right:auto"}

Just like before, we want to duplicate this row. To do this, select the row and press `Shift + D` . Now position the duplicated row on top of the other row, but with a slight offset to the right. The corners of the hexagons of the first row should be positioned between the corners of the second row. You can adjust the distance between the two rows by selecting the second row and selecting the `Object Properties` panel with the small orange square icon. There you can adjust the X and Y position so that the distances between the hexagons are roughly the same.  

![object properties]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/object_properties.png){: style="margin-right: 30px; max-height: 300px"}
![hexagon distance]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/hexagon_distance.png){: style="margin-right: 30px; max-height: 300px"}
![hexagon double row]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/hexagon_rows.png){: style="max-height: 200px"}

At the top right corner is the project tree. There you should now see two objects called `Cylinder` and `Cylinder.001`. Each represents a row of hexagons. To merge them into a single object, select both of them and press `Ctrl + j`. The project tree should now only contain `Cylinder.001`.  
Now we copy these two rows again by selecting them all and pressing `Shift + D` again. Each time you copy, place the resulting rows on top of the previous ones. This way we can create several rows of hexagones. At the end you should have a rectangular field with lots of hexagons.  


<div class="image-with-description-right ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/camera_positioning.png" style="max-height: 300px">
    <p>
        The next thing we want to do is to center the camera. First make sure you are looking at the rows from top down. The best way to do this is to click on the little blue Z on the axis in the top right corner. Then press <code class="language-plaintext highlight-rouge">Ctrl + Alt + Num_0</code> to centre the camera. The camera should roughly cover the whole field. You can move the camera by selecting the camera view, pressing <code class="language-plaintext highlight-rouge">G</code> and moving the mouse to adjust the position, zooming in or out press 
        <code class="language-plaintext highlight-rouge">z</code>.<br>
        <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/blue_z.png"  style="margin-top: 15px; height: 100px">
    </p>
</div>



<div class="image-with-description-left ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/edit_mode.png" style="max-height: 300px">
    <p>
        Next, select all the rows with a left click anywhere in the hexagon rectangle. Switch to <code class="language-plaintext highlight-rouge">Edit Mode</code> by clicking on the drop down menu in the top left hand corner. Now press <code class="language-plaintext highlight-rouge">p</code> and select <code class="language-plaintext highlight-rouge">By loose parts</code>. This can take a few seconds. Switch back to  <code class="language-plaintext highlight-rouge">Object Mode</code>. You should now have all the hexagons as individual objects in the project tree. Select all the hexagons, right click and choose  <code class="language-plaintext highlight-rouge">Set Origin -> Origin to Geometrie</code> . This may also take some time. 
    </p>
</div>

To finish the foreground we switch back into `Object Mode`, select one hexagon and press `o` to switch to the `Proportional editing object mode`. Click the `Move` button on the left toolbar and click the blue arrow that appears near the selected hexagon. Using this arrow, we can now move the hexagon up a little and in the bottom left corner a window saying `Move` should appear.


<div class="image-with-description-right ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/move.png" style="max-height: 200px">
    <p>
        For the <code class="language-plaintext highlight-rouge">Proportional Falloff</code> select <code class="language-plaintext highlight-rouge">Random</code> and change the <code class="language-plaintext highlight-rouge">Proportional Size</code> number to something like 8.0. Then select one of the hexagons again and move it upwards. The surrounding hexagons should now move as well. You can move more than one of the hexagons if you like.
    </p>
</div>

The whole thing should look something like this by now.

![hexagon distance]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/after_propotional_editing_1.png){: height="300" style="margin-right: 30px;"}
![hexagon distance]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/after_propotional_editing_2.png){: height="300"}

Now we need to do some configurations for the rendering. I changed the lamp to `Sun` and reduced the `Strengh` a bit by clicking on the lamp object and selecting the lightbulb 💡 from the toolbar in the bottom right corner, which is the `Object Data Properties` panel. The sun mode makes the lamp behave like the sun would on earth. The light rays go in one direction. You can change the position of the sun and the direction of the rays to suit your needs. I choose the upper right corner. 

<div class="image-with-description-left ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/rendering.png" style="max-height: 100px">
    <p>
        To see the result of your adjustments switch the <code class="language-plaintext highlight-rouge">Viewport Shading</code> to <code class="language-plaintext highlight-rouge">Rendered</code>. This is done by clicking on the outer right circle in the top right toolbar. This will switch to real-time render mode. You should now be able to see the shadows your light is creating. 
    </p>
</div>

<div class="image-with-description-right ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/rendering_mode.png" style="max-height: 200px">
    <p>
        Now let's adjust the render configurations. To get to the <code class="language-plaintext highlight-rouge">Render Properties</code> click on the camera symbol in the right toolbar. As we are going to add some lighting later, we tick the  <code class="language-plaintext highlight-rouge">Bloom</code> checkbox to enable bloom.
    </p>
</div>

<div class="image-with-description-left ">
    <img src="{{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/material.png" style="max-height: 200px">
    <p>
        The last thing we need to do for the foreground is to add a material to the hexagons. We do this by selecting one of the hexagons and switching to the <code class="language-plaintext highlight-rouge">Material Properties</code> which should have a red circle as its icon. In the panel we add a new material by hitting the <code class="language-plaintext highlight-rouge">New</code> Button. Now follow the cofigurations shown in the picture. Basically we set the <code class="language-plaintext highlight-rouge">Surface</code> to <code class="language-plaintext highlight-rouge">Mix Shader</code> and add the <code class="language-plaintext highlight-rouge">Defuse BSDF</code> and <code class="language-plaintext highlight-rouge">Glossy BSDF</code> shaders. Furthermore we change the colour for both shaders to something darker.<br>
        To apply the material to all the hexagons select all the hexagons, press <code class="language-plaintext highlight-rouge">Shift</code> and left click on the hexagon with the material applied. Press <code class="language-plaintext highlight-rouge">Ctrl + L</code> and select <code class="language-plaintext highlight-rouge">Materials</code> in the pop up menu. Now all the hexagons should have this material. You can check by clicking on another hexagon and checking the <code class="language-plaintext highlight-rouge">Material Properties</code> where the material you created earlier should be. <br>
        Now let's render an image of the whole foreground by clicking on the <code class="language-plaintext highlight-rouge">Render</code> in the top menu next to the <code class="language-plaintext highlight-rouge">File</code> and <code class="language-plaintext highlight-rouge">Edit</code> button. 
    </p>
</div>

This should open a new window where you can watch the rendering process. If the resulting image is noisy, you can increase the `Samples` in the `Render Properties` panel, which should right now have a default value of 128. The result should now look something like this.

![rendered image]({{site.baseurl}}/assets/img/{{ page.date | date: "%Y-%m-%d"}}-{{page.title | slugify }}/rendered_image.png){: style="display:block; margin-left:auto; margin-right:auto; max-height:500px"}

Great! You have finished the foreground so far. Take a moment to pat yourself on the back.

---

## The background
Now comes the easy part. The foreground itself already looks quite good. We could stop here and use it as our new wallpaper. But I want something a bit darker. Toget a better contrast. Let us continue with the background to add some colour.

To do this, we will add a new mesh, this is a plane object. We will place the plane under the hexagons and scale it up a little so that it roughly covers all the hexagons. Now we add a material to the plane. Select `Emission` for the `Surface`, then select a colour of your choice and increase the `Strength` of the material to something like 3.5. We have now created a glowing background for our wallpaper, which shines through the small gaps between the hexagons. To see the bloom of the background the "sun light" must not shine to bright. I reduced it to about 8, but it also depends on the distance between the light and the other objects.  
Rendered the whole thing looks like this:

![rendered image with bloom]({{site.baseurl}}/assets/img/foreground_rendered_bloom.png){: style="display:block; margin-left:auto; margin-right:auto; max-height:500px"}

Congratulations you are now finished. I hope you enjoyed creating your own wallpaper and are happy with the result.
