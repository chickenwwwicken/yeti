## crt-aperture
A shader designed to reproduce the look of a high-quality aperture grille CRT TV, such as a Sony PVM or Wega TV. It still looks fairly good at non-integer scales.


## crt-blurpi[¶](https://docs.libretro.com/shader/crt/#crt-blurpi "Reference link to this section")

- A lightweight shader designed to run full speed on Raspberry Pi hardware (hence, the name) and on low-res screens (640x480 or less). It cheats a little by rendering scanlines that match your screen resolution instead of the game resolution, to avoid painful aliasing/Moiré efects on low res screens. Comes in **sharp** and **soft** flavors; use the sharp variant when using interger scaling for best results, and the soft variant otherwise.

## crt-mattias[¶](https://docs.libretro.com/shader/crt/#crt-mattias "Reference link to this section")

- A port of [Mattias' CRT Emulation shadertoy](https://www.shadertoy.com/view/lsB3DV), which is characterized by "crawling" (i.e., scrolling) scanlines. **NewPixie-CRT** is an updated and extended shader from the same author that expands on many of the same ideas used in the original shadertoy.

## dotmask[¶](https://docs.libretro.com/shader/crt/#dotmask "Reference link to this section")

- A basic shader that collects just the isolated dotmask code from several different shaders.

## vt220[¶](https://docs.libretro.com/shader/crt/#vt220 "Reference link to this section")

- Another shadertoy port, this time for [sprash3's vt220 shadertoy](https://www.shadertoy.com/view/XdtfzX), which generates a CRT monitor bezel and then casts dynamic reflections onto it based on the content that's being displayed. This shader works very nicely with classic computer and DOS emulation.

