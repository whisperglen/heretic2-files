# Available in this Heretic 2 repo:

## Articles on the modifications I made for the game:
1. [How to plug-in some C (or C++) code into an existing binary](heretic2_binary_patch.md)
2. [Patching H2Common.dll to add nullchecks when deallocating resources](heretic2_h2common_nullchecks.md)

## Remix PBR and relight Mod contents:
- Updated so far with PBR and extra lights the following maps: ssdocks, sswarehouse, sstown
- Weapon projectiles and effects either spawn a remix light and/or are low-key emmisive to be visible in the dark
- Two flashlights are available (necessary for the untouched maps):
  1. bind f "suckitdown light" -> this will toggle the Light Shrine effect
  2. bind b "rmx_flashlight_toggle" -> this will toggle an over the shoulder front-facing light (not lore accurate but does the job)
- Automatic generation of smoothing surface Normals for a select number of textures
  - see [compnormals.global] inside .ini file
  - rmx_normals 3 will compute Normals for all surfaces, but this will noticeably affect fps
  - rmx_logtextures 1 will log to console all textures that are rendered (use rmx_novis 0 and r_nocull 0 to only log textures visible on-screen)

##  **WARNING**
- This was planned to be a Lazy-man's PBR attempt, to see how far ready made assets and quick texture modification could take me.
- I have taken **a l o t** of creative liberties, I tried to use materials similar to the original, but if the color scheme hurt my eyes, I just picked some other material
- Also, sice I am not replacing 3D assets, some textures look out of place: Remember the original are low quality, therefore higher quality material will just show all the corners that were cut in the original game regarding placement and wrapping


## Installation:
I have used v1.06 because this was working with Remix when I tried it, v1.07 has some visual changes that broke Remix.
1. unzip the mod release over of your Heretic 2 installation
2. unzip the Remix Runtime over the Heretic 2 installation
3. start the game via Heretic2dx.exe (which is just a copy of Heretic2.exe v1.06, to make sure opengl32.dll wrapper is loaded from current directory)
4. DO NOT CHANGE video options (Gamma/Brightness/Contrast will break Remix, don't do it)
    - OpenGL is the mandatory video driver, if you use the widescreen hack, remove it, there is proper Resolution support for OpenGL mode
    - you should be able to change Video Resolution and Fullscreen, keep in mind this causes a Remix reload, and a 10 second hangup is possible when resuming the game
    - Brightness should be changed via Remix slider in the Alt+X menu
    - set V-SYNC via gl_swapinterval 1
5. Bind and use the "Flashlights" there are still areas which are dark
    - bind f "suckitdown light"
    - bind b "rmx_flashlight_toggle"
6. use gl_texturemode GL_NEAREST in console for a pixelated look

## Attributions for Used Assets:
- Created using pbr materials from Poly Haven, licensed under the Creative Commons CC0 1.0 Universal License. https://polyhaven.com/license/
- Created using pbr materials from ambientCG.com, licensed under the Creative Commons CC0 1.0 Universal License. https://docs.ambientcg.com/license/
- Created using pbr materials made in InstaMAT Studio, licensed under a Pioneer License: https://instamaterial.com/licensing/

<a href="https://polyhaven.com">
<img src="./attribution_logos/Poly-Haven-Logo-Colored-Line-Black.png" alt="polyhaven.com" width="200" style="padding: 10px;"/>
</a>
<a href="https://ambientcg.com">
<img src="./attribution_logos/ambientcg-full-color.gif" alt="ambientcg.com" width="200" style="padding: 10px;"/>
</a>
<a href="https://instamaterial.com/">
<img src="./attribution_logos/InstaMAT-Logo-BW-BlackOnWhite.png" alt="instamaterial.com" width="200" style="padding: 10px;"/>
</a>