---
layout: article
title: Creating Seamless Textures
permalink: /guides/seamlessTexture.html
aside:
  toc: true
sidebar:
  nav: guides
---

Nothing about any of the following strategies is unique to Adobe Photoshop, they use fairly fundamental features that most modern image editing software packages should have.

Making an image seamless is just one step of turning a captured photograph into a usable input texture. 

## Offset

Make sure your image is square. Note how many pixels wide it is. Use the **Aspect Ratio** property of the crop tool to ensure this. Next, find the offset tool. In Photoshop, it is *Filter > other > Offset*. Make sure that the Offset is set to wrap, and enter half the canvas size for x and y. 

In Affinity Photo, it is available under *Filter > Distort > Affine*. Set the offset x and the offset y to 50% 

IN GIMP, the feature is available under *Layer > Transform > Offset...*. Change the units to "%" and change the x and y to 50.

This brings the edges that would b touching next to each other in the center of the image. For a tileable texture, we basically haven't done anything yet. Doing the offset makes it much easier to edit the image to blend the seams away. I prefer the clone stamp tool as the main tool to blend the two edges meet. There are no magic tricks to make this easier.

Clone stamp tools are all the same in Photoshop, Affinity , and Gimp. Select the tool, and make sure the brush settings are soft (various property areas). Alt+click to define the brush source (ctrl+click in GIMP), and then paint those pixels somewhere else. It's a simple but incredibly powerful.

### One magic trick to make blending a seam easier

Okay, I lied. There are a few tricks, but it doesn't work on all types of textures. This one will work on less patterned, more "noisy" textures. Before the offset, duplicate the square layer. Flip it horizontally and vertically. (Edit>Transform >Flip Horizontal/Vertical). Now change the opacity of the layer to 50% or so. Consider changing the blending mode until it goes back to looking "good". Now merge the two layers (select both, ctrl+e), and try the offset/blend again.

*In Gimp, Right click a layer and select duplicate. The flip commands are under Image > Transform > Flip Horizontally/Vertically*.

## Clean Up Obvious Repetitions.

A texture can blend seamlessly but it doesn't matter if it always looks like it's repeating. Any really unique element of the texture (that spot of gum on the sidewalk/concrete, etc) should get removed. Clone stamp will do the job, but try selecting around the object in photoshop and going to edit>Fill>Content Aware Fill. Neat. (Sorry Affinity/GIMP users, content-aware fill is a photoshop specialty).

## Skew and Perspective

If your texture is of something patterned, like brick, making the texture seamless is going to be a challenge. The first step is making sure your straight lines are straight. Use the Skew and Perspective tools under the Edit menu in Photoshop, or Filter>Distory>Perspective in Affinity.  For bricks and such tiled textures, it's important to remember that when you are cropping the image, the bricks are the right size so that after you blend the edges together there aren't any super long or tall or weirdly shaped bricks.

## Dodge and Burn

Another step you may want to take before you run the offset is to dodge and burn your image. This just means to brighten and darken parts of it. There are dodge and burn tools in the toolbar. Use a big soft brush with a low opacity, and try to create a uniform brightness. I tend to use a brightness adjustment layer and edit on the mask to do this kind of work, so I can tweak the adjustment layer properties or opacity after the fact.
