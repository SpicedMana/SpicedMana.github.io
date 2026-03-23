---
layout: post
title: "Spiced Controller"
date: 2026-03-22
excerpt: "A Substance Painter Procedural Tool."
tags: [substance painter, image, tool, procedural, spiced mana, spiced controller, mikoxvi, game dev, texturing, 3d, blender]
feature: https://cdnb.artstation.com/p/marketplace/presentation_assets/005/254/305/large/file.jpg?1774211215
comments: true
---

# [Spiced Controller](https://www.artstation.com/a/51211002)
### Substance 3D Painter - Custom Texture Controller
  
Textures shipped with Substance Painter have basic procedural controls such as histogram scan.
I wanted to control my textures similarly instead of tweaking them outside Substance Painter or building big stacks of layered effects and using anchor points.

**Spiced Controller** as an input (for example in the Fill Layer) can add procedural control over the input texture.  
You can use it for stencils, fill layers or anything that has an image input.  
  
This tool adds following controls to input image:

- **Balance**
- **Contrast**
- **Levels**
- **Blur**
- **Invert**
- **Mirror**
- **Randomize / Scatter**
- **Polar Coordinates**

Works with Color and Grayscale.

>Most of it can be achieved by stacking desired effects and manipulating the layers.  
>However, if you have a big stack of effects and you want to exclude some of them from influencing different texture in the stack, then you have to work around it creating separate layers and play with anchor points or mixing the images externally. 
>
> Moreover, it's inefficient to create too many anchor points layer for every custom texture. Substance Painter will reference this data every time you tweak something.  
> Project will start lagging. This tool gathers basic functionalities in one place.
 <br> <br>
# Usage

## Quick setup
Drag and drop the **'Spiced Controller.sbsar'** to Substance Painter asset window. The tool is now installed.

To access the tool simply search for relevant **tags**.  
There are some **extra tags** for quick search. Typing  ***xxx***, ***rrr***, ***ctrl***, ***scsc*** will bring up the tool alone.

Scroll down and find the **Image Inputs** where you can select desired texture.
If you want to use the tool to control Color image instead, then navigate to the top and choose from dropdown menu the **Color_Output** option. 
By default the tool uses **Grayscale_Output**.

After the setup is done you can control your texture.

## Feature breakdown

![*spcd-ctrl_features-fig1*](https://cdnb.artstation.com/p/marketplace/presentation_assets/005/254/407/large/file.jpg?1774228976)

**Balance & Contrast**
The most basic control you want to have over your texture.  
Play with the values to achieve desired outcome.

**Levels**
Another way to control the histogram but with more control.  
By modifying the sliders you can manipulate the contrast, brightness and color balance.  
There are 5 sliders that work exactly like a Levels in any other software including Substance Painter itself.  

Out Low/High are the bottom keys. Lowers the contrast by fading the darkest shadows to gray or bringing the brightest whites to gray.  

Low/Mid/High sliders are the top keys. Mid key is the Gamma while Low and High controls black and white values. You can set Low to 1.0 and High to 0.0 to invert the image. The same rule applies to Out sliders.

**Blur**  
Softens the transition between values.  
You can manually input different number as the slider is limited to 0-1 values.

**Toggles**  
There are several toggles included in the Spiced Controller.

- **Invert**
- **Randomize Switch**
- **Mirror**
- **Use Polar Coordinates**
 
**Invert** is a handy toggle to quickly invert the image.  
Impossible with stock Substance Painter without adding effects.  
Also, not possible to invert in stack without isolating the image. 

**Randomize** is a feature you want to use when you need the texture to be scattered or randomized in some way. You can also use it to create Brush Pattern.  

You don't have to know exactly what does what, just play with it. 
You can also use it if your texture isn't seamless or doesn't tile.
Make it tile by using this feature.

> Briefly explaining the Randomize parameters: 
> 
> Mask Size controls the scatter tile size.  
> Mask Precision is the contrast setting for the scatter tile size.  
> Mask Warping deforms the scatter tile.  
> Disorder scatters the tiles on the UV.  
> Size Variation randomly scales the tiles. You can input a manual value for more control.  
> Tiling creates more tiles and overall scale of the effect.  
> Luminosity Variation randomly darkens tiles.  
> Rotation rotates all tiles.  
> Rotation Variation randomly rotates each tile individually.  

**Mirror** makes the image symmetrical on selected axis.  
You can choose X or Y axis and input custom offset.  
It's great for creating or cleaning up patterns made by hand. 
 There is also an option for corner mirroring.

**Polar Coordinates** are useful if you have a flat UV but you want the texture to be projected as the coordinates are polar (a radial distance from a "pole" and an angle from the polar axis).  
You can create some cool patterns with or texture circular surfaces independently of their flat UV islands.

## Examples

### Using several custom textures
Your mask stack looks something like this:

![*spcd-ctrl_several-textures-fig1*](https://i.imgur.com/5q04B7T.png)

The top fill layer blend mode is set to subtract. You can't simply add another Levels effect to control the subtractive fill layer. If you want to control the top layer you have to either externally edit it and reimport or create another layer with this texture alone, then add your effects and add it back in to the target effect stack using anchor point.

![*spcd-ctrl_several-textures-fig2*](https://cdna.artstation.com/p/marketplace/presentation_assets/005/254/408/large/file.jpg?1774229013)

You may notice, as you add more textures controlled in this manner Substance Painter will start lagging. Also, it's inconvenient as overall layer count rises.

Instead, you may use the Spiced Controller to quickly and efficiently control both textures.

![*spcd-ctrl_several-textures-fig3*](https://cdnb.artstation.com/p/marketplace/presentation_assets/005/254/409/large/file.jpg?1774229015)

This way, the effects stack is tidy and optimal. I often have several textures stacked to achieve desired look and have my assets be textured exactly as I imagined and each mask in this way is original and unique.

With complex material layer setups using Spiced Controller will be not only be more optimal but also tidy. Each custom texture is controlled internally by the tool.

### Using different material channels
If you really like some roughness map or height map and you want to mix it in to your mask stack then you can create an anchor point and add it as an Input to the Spiced Controller.  

For example, the roughness map is usually grayish and lacks contrast. If you were to add it to your stack somewhere in the middle you may discover that you lack artistic control over it.  

Instead of trying to hack it somehow separating prior components and then merging it and brining it to the mask stack you can use the tool to make some simple adjustments inside avoiding the hassle altogether.


### Stencils
You want to paint the details by hand on your model. You have downloaded a crack texture from somewhere or photographed it yourself at a park. Without any adjustments it may not fit your needs as raw photo, so you bring it to image editing software and make a crack texture.

![*spcd-ctrl_stencil-fig1*](https://cdnb.artstation.com/p/marketplace/presentation_assets/005/254/403/large/file.jpg?1774228899)

As you add it to Substance Painter and plug it in as stencil for the paint layer you might feel the need of adjusting. This time you can't use anchor points. You have to adjust the texture outside and reimport. 

![*spcd-ctrl_stencil-fig2*](https://cdna.artstation.com/p/marketplace/presentation_assets/005/254/404/large/file.jpg?1774228910)

Iterations take a lot of time so its optimal to have a tool to do it in procedural way.

### Pattern adjustments
Whether you sculpted an alpha or downloaded a pattern from the internet you might have encountered a problem. Either the pattern isn't symmetrical or has undesired values.  
You need to adjust it.  

Shipped with Substance Painter there are several tools which will enable you to do that.
When I was creating a carpet once and I wanted it to be highly ornate, my mask stack grew bigger. I could work around it by using more layers and so on, but then it's all a mess. You want to change a color of a group of patterns then you need to find it and if you weren't naming everything on the go then you're screwed.  

Besides, if you purchased an "ornamental pack" recently you might have noticed that it's wonky. Maybe it's AI generated, maybe it's made carelessly, maybe it's scanned - doesn't matter - it doesn't fit your needs. It may not be symmetrical, it may lack contrast etc.  

Building a stack made of these would be a nightmare. You would need to edit each pattern individually and pray that it will work fine as you stack them.  
You can evade this issue with ease by using this tool.

### Seamless Texture
Using Randomize I played with the sliders to make the texture seamless.
  
You can diverge from the original as far as you want or even create something entirely different - especially if you blend several images in the same stack.

![*spcd-ctrl_seamless-fig1*](https://cdnb.artstation.com/p/marketplace/presentation_assets/005/254/405/large/file.jpg?1774228929)
![*spcd-ctrl_seamless-fig2*](https://cdna.artstation.com/p/marketplace/presentation_assets/005/254/418/large/file.jpg?1774231489)

### Using Polar Coordinates
To make a really lazy example I modelled a "hat" and quickly unwrapped it using different methods.

![*spcd-ctrl_polar-fig1*](https://i.imgur.com/5q04B7T.png)

Left hat is unwrapped so that there is the least amount of stretch on the brim UV island and Right hat is unwrapped so it is all perfect quads. Each method has its pros and cons but I wanted to highlight how you may mitigate some by using the Spiced Controller.

![*spcd-ctrl_polar-fig2*](https://i.imgur.com/5q04B7T.png)

You might notice that the perfect quad UV has visible problems due to the stretch.
As for the controls and the setup I plugged in the Stripes procedural as the input and just enabled the Polar Coordinates switch.

![*spcd-ctrl_polar-fig3*](https://i.imgur.com/5q04B7T.png)

I turned down the Shift to 0 so the stripes are straight.

You may create unique patterns using this feature. To visualize it better I mapped the Stripes onto a plane.
![*spcd-ctrl_polar-fig4*](https://i.imgur.com/5q04B7T.png)
![*spcd-ctrl_polar-fig5*](https://i.imgur.com/5q04B7T.png)
Only changing the Shift slightly you get a different result.

I created this pattern really quicky using some stock Substance Painter texture I picked randomly (not a cherrypick)
![*spcd-ctrl_polar-fig6*](https://i.imgur.com/5q04B7T.png)
![*spcd-ctrl_polar-fig7*](https://i.imgur.com/5q04B7T.png)

You can then edit it further by manually masking it with paint layer or whatever you need and then once again use the tool to modify it.

![*spcd-ctrl_polar-fig8*](https://i.imgur.com/5q04B7T.png)
![*spcd-ctrl_polar-fig9*](https://i.imgur.com/5q04B7T.png)

In this case I used bottom output as an anchor point for the final output and added some paint to remove remnants of the noise which I didn't like.

### Your own way
I'm certain this tool will be useful to anyone who loves to manipulate and blend textures. You will come up with your own ways the tool will be useful for you. I'm using it very often, especially when using my own textures created outside Substance suite in the Substance suite. This is a basic tool puts together fundamental controls so you can adjust your textures and realize your vision.  

 <br> <br>
Download
=
## [Artstation](https://www.artstation.com/a/51211002)