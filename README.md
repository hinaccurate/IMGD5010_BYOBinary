![maCart_banner](https://github.com/user-attachments/assets/28c50459-1ec9-4e81-ab51-a97e54746c49)

# maCart
_Code yourself some **ma**caroni **art** with **C**-shaped pasta._
###### last updated: January 21, 2025

<a name="index"></a>
## Index

* [Quick Start](#quick-start)
  * First steps
  * List of codes
  * Design clocks
    
* [Commands in Depth](#commands-in-depth)
  * Macaronus
  * Arrange
  * Draw
  * Color
 
* [Sample Program](#sample-program)
  * Code
  * Output with outlined macaronus units
  * Output without outline

<hr>

<a name="quick-start"></a>
# Quick Start
### First steps

1. Get your art materials together:
   - A box of macaroni, glue, paper, and crayons or similar, OR--
   - Just the paper and something to draw and color with.

2. Starting at the top-left corner of your paper, use maCart codes to place or draw macaroni shapes
   - If you're reading this for the first time, jump down to the [`0000`](#0000) explainer to learn more about the basic unit of a maCart drawing, the 'macaronus'

<a name="list-of-codes"></a>
### List of codes

To learn more about each code, click on the link for examples.

| Code  | What happens |
| --- | --- |
| **Macaronus** | |
| [`0000`](#0000)  | Make a new macaronus on your paper  |
| [`0001`](#0001)  | Add a macaroni to the current cell  |
| [`0010`](#0010)  | Move to the next cell in the macaronus  |
| **Arrange** | |
| [`0011`](#0011)  | Flip macaroni |
| [`0100`](#0100)  | Rotate macaroni |
| [`0101`](#0101)  | Push macaroni against a side of the cell |
| [`0110`](#0110)  | Touch macaroni to two sides of the cell |
| **Draw** | |
| [`0111`](#0111)  | Change crayon color |
| [`1000`](#1000)  | Draw line between the center of the cell to a side |
| [`1001`](#1001)  | Draw a dot in the center of the cell |
| **Color** | |
| [`1010`](#1010)  | Fill in a quarter of the cell |
| **Advanced** | |
| [`1011`](#1011)  | Clear previous macaronus and restart it |
| [`1100`](#1100)  | Copy previous macaronus |
| [`1110`](#1110)  | Paste copied macaronus |

<a name="design-clocks"></a>
### Design clocks

Some codes can be used multiple times to change a condition of the macaroni or the macaronus. Imagining clocks (and clockwise movement) helps minimize the number of commands needed to implement a lot of different options without having to waste additional commands to individually label specific settings.  

<a name="rotation-clock"></a>
* **Rotation clock**
  - Use with `0100` _after_ the `0001` "add a macaroni" command.
  - Can be used interchangeably with the **Arrange** commands (`0011`, `0100`, `0101`, and `0110`) to create the effect required.
  - Each instance advances the rotation 90 degrees until it returns to 0.
  - From a macaroni's starting position (the C-shape), there are a maximum of 3 instances before the clock restarts at the top.
  - This means that, practically, you could code `0100` ten times in a row and still end up with a macaroni rotated just 180 degrees.
    
![maCart-32](https://github.com/user-attachments/assets/2649e230-8285-4ad4-999a-a315fb686208)

<a name="push-clock"></a>
* **Push clock**
  - Use with `0101` to _after_ the `0001` "add a macaroni" command.
  - Can be used interchangeably with the **Arrange** commands (`0011`, `0100`, `0101`, and `0110`) to create the effect required.
  - Each instance advances clockwise the side of the cell the macaroni pushes up against, starting with the "top".
  - From a macaroni's starting position (a centered C-shape), there are a maximum of 4 instances before the clock restarts at the top. It does _not_ return to center.
  - This means that, practically, you could code `0101` ten times in a row and still end up with a macaroni pushed to the bottom side of the cell.
    
![maCart-33](https://github.com/user-attachments/assets/c61ea105-3acc-41bf-8e2d-44d054dfde08)

<a name="touch-clock"></a>
* **Touch clock**
  - Use with `0110` _after_ the `0001` "add a macaroni" command.
  - Can be used interchangeably with the **Arrange** commands (`0011`, `0100`, `0101`, and `0110`) to create the effect required.
  - Each instance of `0110` advances which two sides of the cell the macaroni touches clockwise, starting with "top-right". 
  - From a macaroni's starting position (the C-shape), there are a maximum of 4 instances before the clock restarts at the top. It does _not_ return to center.
  - This means that, practically, you could use `0110` ten times in a row and still end up with a macaroni touching "right-bottom".
    
![maCart-34](https://github.com/user-attachments/assets/a371152a-3f1a-4284-8a49-0647f9de5e70)

<a name="color-clock"></a>
* **Color clock**
  - Use with `0111` _before_ the **Draw** and **Color** commands (`1000`, `1001`, and `1010`).
  - Each instance advances the color clockwise from clear (no crayon), to Red, Yellow, Blue, Purple, Green and Black.
  - From a macaronus cell's starting color (clear), there are a maximum of 6 instances before the clock restarts at the top. It does _not_ return to clear.
  - This means that, practically, you could code `0111` ten times in a row and still end up with a Purple crayon.
    
![maCart-35](https://github.com/user-attachments/assets/ee6f4a8c-4b52-4e9f-81c0-1f5dcbee87d1)

<a name="line-clock"></a>
* **Line clock**
  - Use with `1000` _after_ the crayon-color code `0111`.
  - Each instance advances the line's endpoint clockwise, starting with the "noon" position (top-center). _Any_ instance of `1000` creates a line (though whether it's visible depends on the color crayon you're using).
  - From the starting position, there are a maximum of 8 instances before the clock restarts at the top--but each use requires that you rechoose your crayon.
  - This means that, practically:
    - If you don't call `0111` first and choose your color, you could use `1000` ten times in a row and still end up with no lines.
    - If you call `0111` once and then `1000` three times, you'd have a red line in the "noon" position (center to top-center) but no other visible lines.
    - If you call `0111 1010` four times in a row, you would have four red lines pointing from the center to the "noon", "1 o'clock", "2 o'clock" and "3 o'clock" positions.
      
![maCart-36](https://github.com/user-attachments/assets/25ab41d3-169a-40ac-a3d3-5d9489733d63)

<a name="quarter-coloring-clock"></a>
* **Quarter coloring clock**
  - Use with `1010` _after_ the crayon-color code `0111`.
  - Each instance advances the quarter being colored in clockwise, starting with "top-right". 
  - From the starting quarter, there are a maximum of 4 instances before the clock restarts at the top--but each use requires that you rechoose your crayon.
  - This means that, practically:
    - If you don't call `0111` first and choose your color, you could use `1010` ten times in a row and still end up with a clear cell.
    - If you call `0111` once and then `1010` three times, you'd have a red top-right quarter and then clear bottom-right and bottom-left quarters.
    - If you call `0111 1010` four times in a row, the entire cell would be red.
      
![maCart-37](https://github.com/user-attachments/assets/1a48204a-923b-4540-8dd4-fd7b3a6380a0)

&rarr; _Go back to [Index](#index)_

<hr>

<a name="commands-in-depth"></a>
# Commands in Depth
## Macaronus

<a name="0000"></a>
### `0000`: Make a new macaronus on your paper 

  * To help keep track of your work, imagine--or draw--a grid made up of 4 smaller squares (cells). Using the `0000` code, put that grid in the top left of your paper. We can call this working grid a **Macaronus**.

![maCart-1](https://github.com/user-attachments/assets/a735ba33-b949-488a-a39c-e01207aeae86)
![maCart-2](https://github.com/user-attachments/assets/41eca5f8-bab8-4e33-ba26-fd590ffb69ec)

  * The macaronus starts empty (the faint lines in the below examples are just to demonstrate the cells in the grid). Using the 'add macaroni' code (`0001`), start at the top left of the macaronus, and work in that cell using the **Arrange**, **Draw**, or **Color** codes until you're ready to move clockwise to the next cell (using `0001`).

![maCart-6](https://github.com/user-attachments/assets/7b0078bf-d305-4185-9f03-6bdbdc9ffcf7)
![maCart-7](https://github.com/user-attachments/assets/1e0e9b4d-45cc-4ebd-8a40-3eac093e504c)
    
  * When you've filled your macaronus, you can either finish your maCart drawing--
 
![maCart-11](https://github.com/user-attachments/assets/0bef1e43-7dea-4295-8c72-fd7ba9a59ebf)
 
--or add a new macaronus (with the `0000` code) to the right of the previous one.

![maCart-4](https://github.com/user-attachments/assets/290915b7-9ff7-438f-b69e-81ebe24a6456)

  * If you reach the end of your paper but aren't done yet, go back to the left side of your paper and add your next macaronus directly under the previous row (like a typewriter zinging back to the start of the next line).

![maCart-5](https://github.com/user-attachments/assets/ef67f389-5783-4aca-912b-b07f4e017ab3)

<a name="0001"></a>
### `0001`: Add a macaroni to the current cell

* The basic maCart shape is the "macaroni", and the first macaroni placed in the macaronus always starts in the top-left cell, rotated to make a "C" (like "ma**C**art").

![maCart-6](https://github.com/user-attachments/assets/14d68415-a6c7-4b2f-bc9a-b9ea6f022aa6)

* Use the **Arrange** codes--

![maCart-7](https://github.com/user-attachments/assets/f7211e58-9441-4671-8566-894790b028a8)

--**Draw** codes--

![maCart-12](https://github.com/user-attachments/assets/06371df7-4419-4a7d-9226-e7ea844ced8d)

--and **Color** codes-- 

![maCart-13](https://github.com/user-attachments/assets/4d4ee47b-71ed-4cee-9a71-66c2aeeb44a9)

--to adjust the macaroni in the cell until you're ready to move clockwise to the next cell (using `0010`).

![maCart-18](https://github.com/user-attachments/assets/34021a1d-328d-4faf-af26-6c93619bda69)

<a name="0010"></a>
### `0010`: Move to the next cell in the macaronus

* When you move to the next cell, you can choose to add a macaroni (with `0001`)--

![maCart-22](https://github.com/user-attachments/assets/eaf44176-8e7c-4b47-bb90-c408f0e3834b)

--or you can use the **Draw** and **Color** codes instead--

![maCart-21](https://github.com/user-attachments/assets/25129e11-1b15-4c33-947c-8a69d3391cc1)

--or you can move to the next cell and add a macaroni to _that_ cell.

![maCart-23](https://github.com/user-attachments/assets/53f86f2c-ecca-4d8e-aa9f-ffe5ef914797)

&rarr; _Go back to [List of Codes](#list-of-codes)_\
&rarr; _Go back to [Index](#index)_

***

## Arrange

<a name="0011"></a>
### `0011`: Flip macaroni

* This code flips the macaroni on its vertical axis. This means that if your macaroni is still in its starting position, the flip will keep it still C-shaped, just reversed:

![maCart-6](https://github.com/user-attachments/assets/8e2a8545-5b49-45d3-b8dc-f26f5a3a3aa8)
![maCart-24](https://github.com/user-attachments/assets/83b12dd2-0274-429d-84e8-31a15a4410d4)

* If your macaroni has been rotated (using the `0101` code) and then flipped, it would look like this:

![maCart-25](https://github.com/user-attachments/assets/b264a954-409c-446e-bd94-2d2797536f5d)
![maCart-26](https://github.com/user-attachments/assets/d3a896ce-804a-4e02-be47-9190db2bf238)

...and so on.

<a name="0100"></a>
### `0100`: Rotate macaroni

* The macaroni always starts upright in a C-shape.

![maCart-6](https://github.com/user-attachments/assets/78721a74-0849-42db-ba7d-8541251f249a)

* To rotate it, add `0100`-- this turns the macaroni 90 degrees.

![maCart-25](https://github.com/user-attachments/assets/5aeaf336-d718-43e9-be9b-7912da91c5df)

* To rotate the macaroni more, use the [Rotation clock](#rotation-clock) to track how many instances of the code you need to move the macaroni another turn clockwise. The below would be `0100 0100 0100`:

![maCart-27](https://github.com/user-attachments/assets/ae08c7bf-416e-4288-9201-9b8af7ab79f4)


<a name="0101"></a>
### `0101`: Push macaroni against a side of the cell

* The macaroni always starts upright in a C-shape, but after the flipping and/or rotating it, you can also choose to push it up against a side of the cell to help connect macaroni later.

* To push the macaroni against the top of the cell, add `0110`. If the macaroni already fills your cell in its current arrangement, it may not make much of a difference:

![maCart-28](https://github.com/user-attachments/assets/e3ce04d0-148f-4441-9628-65db7955e14d)

* But to push the macaroni against a different side, use the [Push clock](#push-clock) to track how many instances of the code you need to push the macaroni to the next side, in clockwise order. The below would be `0101 0101`:
  
![maCart-29](https://github.com/user-attachments/assets/58366749-a60f-4eff-b7c6-7b60951a3cde)

<a name="0110"></a>
### `0110`: Touch macaroni to two sides of the cell

* The macaroni always starts upright in a C-shape, but after the flipping and/or rotating it, you can also choose to angle it by pushing it against two sides of the cell.

* To make the macaroni touch the top and right side of the cell, add `0110`:

![maCart-31](https://github.com/user-attachments/assets/0edd1e3f-cd60-4e66-b32f-b513ce730465)

* But to angle the macaroni differently, use the [Touch clock](#touch-clock) to track how many instances of the code you need to angle the macaroni clockwise to the next two sides. The below would be `0110 0110`:

![maCart-30](https://github.com/user-attachments/assets/90aa73c6-075c-4947-8bb0-f7b7e20cc275)

&rarr; _Go back to [List of Codes](#list-of-codes)_\
&rarr; _Go back to [Index](#index)_

***

## Draw

<a name="0111"></a>
### `0111`: Change crayon color 

* The color always starts clear (i.e., no crayon).

* To change (use) a color, add `0111` before one of your **Draw** or **Color** codes. Note! You'll need to use the crayon code _each time_ you want to draw or color! (See the [Design clocks](#design-clocks) for examples.)
  
* Use the [Color clock](#color-clock) to track how many instances of the code you need to get the color you want. The color starts clear (no crayon), and advances to Red, Yellow, Blue, Purple, and Green before returning to clear.

<a name="1000"></a>
### `1000`: Draw line between the center of the cell to a side 

* The line always starts from the center of the cell with an endpoint of "noon" (top-center), and the color always starts clear.

* Use the [Line clock](#line-clock) to track how many instances of the code you need to draw the line where you want it. Use the [Color clock](#color-clock) to track which color you want your line to be.
  
* To change the color, use the `0111` crayon-color code before each use of `1000`. Note! You'll need to use the crayon code _each time_ you want to draw or color! (See the [Design clocks](#design-clocks) for examples.)
  
* Depending on the order of your coding, you can either draw a line under (common), around (common), or on top of (uncommon) the macaroni. The same goes for dots (`1001`) and filled in quarters (`1010`).

![maCart-38](https://github.com/user-attachments/assets/e64a9566-0efa-496b-aa27-10e9f652f6e2)

<a name="1001"></a>
### `1001`: Draw a dot in the center of the cell 

* The color of the dot always starts clear. 

* To change the color, use the `0111` crayon-color code before each use of `1001`. Note! You'll need to use the crayon code _each time_ you want to draw or color! (See the [Design clocks](#design-clocks) for examples.) 

* Depending on the order of your coding, you can either add a dot in a blank cell (common), in a space unoccupied by macaroni (common), or on top of the macaroni (uncommon). The same goes for lines (`1000`) and filled in quarters (`1010`).

![maCart-39](https://github.com/user-attachments/assets/57fe3699-e876-4698-a4aa-81f2eb0a2bab)

&rarr; _Go back to [List of Codes](#list-of-codes)_\
&rarr; _Go back to [Index](#index)_

***

## Color

<a name="1010"></a>
### `1010`: Fill in a quarter of the cell 

* The working quarter of the cell always starts with the top-right, and the color always starts clear.
  
* Use the [Quarter coloring clock](#quarter-coloring-clock) to track how many instances of the code you need to color which quarter you want. Use the [Color clock](#color-clock) to track which color you want your quarter to be.
  
* To change the color, use the `0111` crayon-color code before each use of `1010`. Note! You'll need to use the crayon code _each time_ you want to draw or color! (See the [Design clocks](#design-clocks) for examples.)
  
* Depending on the order of your coding, you can either color under (common), around (common), or on top of (uncommon) the macaroni. The same goes for dots (`1001`) and lines (`1000`).

![maCart-40](https://github.com/user-attachments/assets/1bcaed48-6fe1-424d-acd6-d4e10ef11607)

&rarr; _Go back to [List of Codes](#list-of-codes)_\
&rarr; _Go back to [Index](#index)_

***

## Advanced

<a name="1011"></a>
### `1011`: Clear previous macaronus and restart it 

* This is just a way to erase and rework your maCart drawing--treat it like a backspace, moving your working area back one macaronus.

<a name="1100"></a>
### `1100`: Copy previous macaronus 

* It can be onerous to fill an entire page (or to code one). If you have an empty macaronus, you can just use `0000` to progress to the next working space, but if you have a pattern you want to repeat across multiple macaronus units, use `1100`.

* You can also edit a copied macaronus as you would a `0000`, which allows for small variations in a more complex pattern.

* Note! This code overwrites any previously copied macaronus.

<a name="1110"></a>
### `1110`: Paste copied macaronus 

* Provided there's a copied macaronus already, `1110` can be used in place of `0000`.

* Pasted macaronus units can be edited using the **Arrange**, **Draw**, and **Color** codes. Just be aware that your starting point in each cell may be different (based on the [Design Clock](#design-clocks) options).

&rarr; _Go back to [List of Codes](#list-of-codes)_\
&rarr; _Go back to [Index](#index)_

<hr>

<a name="sample-program"></a>
# Sample Program

## Code
`0000`\
`0000`

`0000`\
`0010 0010 0010 0001`\
`0100`\
`0101 0101 0101`

`0000`\
`0000`\
`0000`

`0000`\
`0010 0001`\
`0101 0101`

`0000`\
`0111 0111 0111 0111 1010`\
`0111 0111 0111 0111 1010 1010`\
`0111 0111 0111 0111 1010 1010 1010`\
`0111 0111 0111 0111 1010 1010 1010 1010`\
`0111 0111 0111 1001`\
`0010 0001 0100 0100 0101 0101 0101 0101`\
`0010 0001 0011 0110 0110 0110`\
`0010 0001 0100 0100 0100 0101`

`0000`\
`0000`

`0000`\
`0010`\
`0010 0111 0111 0111 0111 0111 1000 1000 1000 1000`

`0000`\
`0010 0010`\
`0010 0001 0101 0101`\
`0010 0111 0111 0111 0111 0111 1000 1000 1000 1000`

`0000`\
`0001 0100 0101 0101 0101`\
`0010 0001 0110 0110 0110 0110`\
`0010 0111 0111 0111 0111 0111 1000 1000 1000 1000 1000 1000`\
`0010 0111 0111 0111 0111 0111 1000 1000 1000 1000 1000 1000`

`0000`\
`0000`

`0000`\
`0010 0111 0111 0111 0111 0111 1010`

`0000`\
`0111 0111 0111 0111 0111 1010`\
`0111 0111 0111 0111 0111 1010 1010 1010 1010`\
`0010 0111 0111 0111 0111 0111 1010`\
`0111 0111 0111 0111 0111 1010 1010 1010 1010`

`1100`\
`1110`\
`0000`\
`0000`

## Output with outlined macaronus units

![maCart-41](https://github.com/user-attachments/assets/bcbe57fb-5001-4c4d-b3d2-628795cf5599)

## Output without the outline

![maCart-42](https://github.com/user-attachments/assets/517f09e2-0081-45eb-86ec-5b2a21504ade)
