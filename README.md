![maCart_banner](https://github.com/user-attachments/assets/28c50459-1ec9-4e81-ab51-a97e54746c49)

# maCart
_Code yourself some **ma**caroni **art** with **C**-shaped pasta._
###### last updated: January 19, 2025

<a name="index"></a>
## Index

* [Quick Start](#quick-start)
  * First step
  * List of codes
    
* [Commands In-Depth](#commands-in-depth)
  * Macaronus
  * Arrange
  * Draw
 
* [Sample Programs](#sample-programs)

<hr>

<a name="quick-start"></a>
# Quick Start
### First step

1. Get your art materials together:

  * A box of macaroni, glue, paper, and crayons or similar.
OR
  * Just the paper and something to draw and color with.

2. Use maCart codes to place or draw macaroni on your paper

  * To help keep track of your work, imagine--or draw--a grid made up of 4 smaller squares (cells), and put it in the top left of your paper. We can call this working grid a 'macaronus'.
  * Starting at the top left of the macaronus, work in that cell until you're ready to move clockwise to the next one.
  * When you've filled your macaronus, you can either finish your maCart drawing or add a new macaronus (with the `0000` code) to the right of the previous one.
  * If you reach the end of your paper but aren't done yet, go back to the left side of your paper and add your next macaronus directly under the previous row.

### List of codes

| Code  | What happens |
| --- | --- |
| **Macaronus** | |
| `0000`  | Make a new macaronus on your paper  |
| `0001`  | Add a macaroni--turned like a "C"--to the current cell  |
| `0010`  | Move to the next cell in the macaronus  |
| `0011`  | Clear previous macaronus and restart it  |
| **Arrange** | |
| `0100`  | Flip macaroni on its vertical axis  |
| `0101`  | Rotate macaroni (clockwise 90 degrees) |
| `0110`  | Push macaroni to the cell's side (starting clockwise from top) |
| `1001`  | Push macaroni to touch two sides 
| **Draw** | |
| `1100`  | Draw line between two macaroni ends |
| `1010`  | Draw line between two macaroni middles |
| `1000`  | Change color of  |
| `1110`  | 


&rarr; Go back to [Index](#index)

<hr>

<a name="about"></a>
# About
### What is macaroni art?

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_TK_

&rarr; Go back to [Index](#index)

<a name="maCart-basics"></a>
## maCart Basics
### A single macaronus

For our purposes, a single piece of digital macaroni art drawn with this program is called a "maCart drawing", and the basic unit of a maCart drawing is a "macaronus": a 4-cell, diamond-shaped grid, where each cell can either have a piece of pasta added or skipped and left empty. Each piece of pasta, as it's placed, can be flipped, rotated, have smaller or larger shadows of varying levels of transparency and either along the convex or concave side.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Examples: 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_TK_ 

maCart drawings are composed of one or more macaronus units, allowing for very small and simple digital pieces mimicking children's compositions or for infinite-canvas mosaics.

### Starting positions

* The macaronus starts empty (the faint lines in the below examples are just to demonstrate the cells in the diamond).

![maCart-1](https://github.com/user-attachments/assets/75886e30-590b-4918-8e90-60e50d3dcaa9)

* The basic pasta shape is "macaroni", and the first macaroni placed in the macaronus always starts in the top cell, rotated to make a "C".

![maCart-6](https://github.com/user-attachments/assets/f7159b44-773a-468f-bba9-8d74848d2b39)

* Subsequent macaroni are placed clockwise until the macaronus is filled, but macaroni can continue to be layered over one another until the command to add a new macaronus to the maCart drawing is given.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Example: _TK_

* Colors can be changed through different commands, but don't have to be.
  
  * The macaroni is yellow.
  * The lighting on the macaroni is coming from directly above, with no shadows (i.e., 100% transparent).
  * ...But if the shadow _was_ visible, it would be on the convex side of the macaroni.
  * The background color of the macaronus starts as "kraft" (cardboard).
  * The implied "glue" that creates a macaronus perfectly aligned with the pasta (i.e., 100% transparent).

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Example: _TK_

### Always clockwise...

When composing a maCart drawing, the macaronus starts in the center of the digital canvas--and just as a macaronus is composed clockwise starting from the upper-left, so too are maCart drawings composed of new macaronus units added in a clockwise spiral around the central macaronus. Every new macaroni, and every new macaronus, starts as near to the top of the "clock" as possible.

![maCart-1](https://github.com/user-attachments/assets/7165ac4f-43e9-4891-ab23-a9e2bd10c307) ![maCart-6](https://github.com/user-attachments/assets/6df7702b-7193-4062-947c-675adda09a1a) ![maCart-5](https://github.com/user-attachments/assets/ced4d81a-da4c-4c69-aa64-d959a72f9ca7)

Each new macaroni can be rotated clockwise as well, on either a macro or micro level.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Example: _TK_

While the macaroni can be layered, the macaronus units spiral out as they get added on. If you imagine each side of the macaronus labeled with letters (again, starting clockwise from the upper-left), a macaronus would look like this:

![maCart-7](https://github.com/user-attachments/assets/5bb89338-03f6-45fa-befc-fa67095733a4)

Each new macaronus is added so that one side is aligned to specific side of the previous, starting from the upper-left and circling clockwise. The pattern is:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_AC(1), BD(1), CA(2), DB(2), AC(3), BD(3), CA(4), DB(4), AC(5), BD(5)..._

So in practice, every time a new macaronus is created, the pattern develops in a spiral from the center and the overall maCart drawing zooms out to stay on the canvas.

![maCart-7](https://github.com/user-attachments/assets/8d2f5860-adad-4650-bc61-992a0553fd6a)
![maCart-8](https://github.com/user-attachments/assets/6d14e4a5-f1eb-4466-a3d2-dd67bb93d303)
![maCart-9](https://github.com/user-attachments/assets/e87ac5da-132f-4e37-ab8e-e254bed17f70)
![maCart-10](https://github.com/user-attachments/assets/912e0e9f-30c5-4ea0-83b4-8312c9acaaf0)
![maCart-11](https://github.com/user-attachments/assets/68d27ac5-57a6-4b59-afe4-1525d372d65b)
![maCart-12](https://github.com/user-attachments/assets/2d0430ec-a0d0-4651-a678-19d653881a12)
![maCart-13](https://github.com/user-attachments/assets/e809758b-7549-432f-96b8-8ca440823d1d)
![maCart-14](https://github.com/user-attachments/assets/10136351-dcb7-47c1-bc45-e8f0b7e22b75)
![maCart-15](https://github.com/user-attachments/assets/529fae0b-c259-482b-b164-beb88b2a566b)
![maCart-16](https://github.com/user-attachments/assets/bb805539-2504-4f51-851d-58137b7b5eb6)

### ...Using design clocks

Imagining clocks (and clockwise movement) helps minimize the number of commands needed to implement a lot of different options without having to waste additional commands to individually label specific settings.

* Color clock

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Example: _TK_

* Light clock
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Example: _TK_

* Shadow clock
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Example: _TK_

* Glue clock

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Example: _TK_

&rarr; Go back to [Index](#index)

<a name="command-list"></a>
# Command List
### Macaronus

* **1000** - Makes a new macaronus on the canvas

* **0010** - Add a macaroni to the current cell

* **0100** - Move to next cell in macaronus

* **1110** - Delete previous macaronus
  
* **0000** - Clear canvas

### Arrange

* **1001** - Flip macaroni on its vertical axis

* **0111** - Macro rotate macaroni (clockwise 90 degrees)

* **0001** - Micro rotate macaroni (clockwise 5 degrees)

### Art

* **0011** - Changes the color of the macaronus's construction paper by advancing the "color clock" once for each command
  * In order: Kraft, Red, Yellow, Blue, Black, and White

* **1011** - Increases the opacity of the macaroni's shadow by advancing the "shadow clock" once for each command
  * In order: 0% transparency Black, 25% transparency, 50% transparency, and 75% transparency

* **1101** - Increases the size of the macaroni's shadow by advancing the "light clock" once for each command 
  * In order: 0% larger than macaroni, 25% larger, 50% larger, and 75% larger

* **0101** - Shift the shadow from the convex side of the macaroni to the concave

### Advanced Art

* **1100** - Changes glue color by advancing the "glue clock" once for each command
  * In order: White at 100% transparency, then Red, Yellow, Blue, Purple, and White at 15% transparency)

* **1111** - Pasta size (1 macaroni fills entire macaronus, can be used instead of 00 but overwrites any use of the 000 arrangement command)

* **0110** - Copy previous macaronus (overwriting any previous copied macaronus)

* **1010** - Paste copied macaronus (in the same pattern as the 1000 new macronus command)

&rarr; Go back to [Index](#index)

<a name="examples"></a>
## Examples

1. Make a pinwheel

```
1000
0010 1011 1101 1101 0101 0100
0010 0111 1011 1101 1101 0100
0010 1001 1011 1101 1101 0101 0100
0010 0111 1001 1011 1101 1101 0100
```
![maCart-4](https://github.com/user-attachments/assets/458cba6f-5b59-4ad9-93b4-ae9849255eff)


2. Make a repeating pattern

```
1000
0011 0011 0011 0011 0011
0010 0100
0010 0111 1100 1100 1100 1100 0100
0010 1001 0100
0010 0111 1001 1100 1100 1100 1100 0100
0110
1010 1010 1010 1010 1010 1010 1010 1010
```
![maCart-2](https://github.com/user-attachments/assets/27e17528-e51e-4e17-a1ca-a5dc2459da6a)


3. Make a dinosaur

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_TK_

&rarr; Go back to [Index](#index)

<a name="inspiration"></a>
## Inspiration
### Real-life macaroni art

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_TK_

### Other related macaroni art 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_TK_

&rarr; Go back to [Index](#index)
