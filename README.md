![maCart_banner](https://github.com/user-attachments/assets/28c50459-1ec9-4e81-ab51-a97e54746c49)

# maCart
_Code yourself some **ma**caroni **art** with **C**-shaped pasta._
###### last updated: January 21, 2025

<a name="index"></a>
## Index

* [Quick Start](#quick-start)
  * First step
  * List of codes
    
* [Commands in Depth](#commands-in-depth)
  * Macaronus
  * Arrange
  * Draw
  * Color
 
* [Sample Programs](#sample-programs)

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
| [`0001`](#0001)  | Add a macaroni--turned like a "C"--to the current cell  |
| [`0010`](#0010)  | Move to the next cell in the macaronus  |
| [`0011`](#0011)  | Clear previous macaronus and restart it  |
| **Arrange** | |
| [`0100`](#0100)  | Flip macaroni |
| [`0101`](#0101)  | Rotate macaroni |
| [`0110`](#0110)  | Push macaroni against a side of the cell |
| [`0111`](#0111)  | Push macaroni touch two sides of the cell |
| **Draw** | |
| [`1000`](#1000)  | Change crayon color |
| [`1001`](#1001)  | Draw line between the center of the cell to the top |
| **Color** | |
| [`1010`](#1010)  | Draw a dot in the center of the cell |
| [`1011`](#1011)  | Fill in a quarter of the cell |

&rarr; Go back to [Index](#index)

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
### `0001`: Add a macaroni--turned like a "C"--to the current cell

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

<a name="0011"></a>
### `0011`: Clear previous macaronus and restart it 

* This is just a way to erase and rework your maCart drawing--treat it like a backspace, moving your working area back one macaronus.

&rarr; Go back to [List of Codes](#list-of-codes)\
&rarr; Go back to [Index](#index)


## Arrange

<a name="0100"></a>
### `0100`: Flip macaroni

* This code flips the macaroni on its vertical axis. This means that if your macaroni is still in its starting position, the flip will keep it still C-shaped, just reversed:

![maCart-6](https://github.com/user-attachments/assets/8e2a8545-5b49-45d3-b8dc-f26f5a3a3aa8)
![maCart-24](https://github.com/user-attachments/assets/83b12dd2-0274-429d-84e8-31a15a4410d4)

* If your macaroni has been rotated (using the `0101` code) and then flipped, it would look like this:

![maCart-25](https://github.com/user-attachments/assets/b264a954-409c-446e-bd94-2d2797536f5d)
![maCart-26](https://github.com/user-attachments/assets/d3a896ce-804a-4e02-be47-9190db2bf238)

...and so on.

<a name="0101"></a>
### `0101`: Rotate macaroni

* The macaroni always starts upright in a C-shape.

![maCart-6](https://github.com/user-attachments/assets/78721a74-0849-42db-ba7d-8541251f249a)

* To rotate it, add `0101`-- this turns the macaroni 90 degrees.

![maCart-25](https://github.com/user-attachments/assets/5aeaf336-d718-43e9-be9b-7912da91c5df)

* To rotate the macaroni more, add an instance of the code to move the macaroni another turn clockwise. The below would be `0101 0101 0101`:

![maCart-27](https://github.com/user-attachments/assets/ae08c7bf-416e-4288-9201-9b8af7ab79f4)


<a name="0110"></a>
### `0110`: Push macaroni against a side of the cell

* The macaroni always starts upright in a C-shape, but after the flipping and/or rotating it, you can also choose to push it up against a side of the cell to help connect macaroni later.

* To push the macaroni against the top of the cell, add `0110`. If the macaroni already fills your cell in its current arrangement, it may not make much of a difference:

![maCart-28](https://github.com/user-attachments/assets/e3ce04d0-148f-4441-9628-65db7955e14d)

* But to push the macaroni against a different side, add another instance of the code to push the macaroni to the next side, in clockwise order. The below would be `0110 0110`:
  
![maCart-29](https://github.com/user-attachments/assets/58366749-a60f-4eff-b7c6-7b60951a3cde)

<a name="0111"></a>
### `0111`: Push macaroni touch two sides of the cell

* The macaroni always starts upright in a C-shape, but after the flipping and/or rotating it, you can also choose to angle it by pushing it against two sides of the cell.

* To push the macaroni against the top and right side of the cell, add `0111`:

![maCart-31](https://github.com/user-attachments/assets/0edd1e3f-cd60-4e66-b32f-b513ce730465)

* But to angle the macaroni differently, add another instance of the code to angle the macaroni clockwise to the next two sides. The below would be `0111 0111`:

![maCart-30](https://github.com/user-attachments/assets/90aa73c6-075c-4947-8bb0-f7b7e20cc275)


&rarr; Go back to [List of Codes](#list-of-codes)\
&rarr; Go back to [Index](#index)


## Draw

<a name="1000"></a>
### `1000`: Change crayon color 

* starts clear, but add another instance of the code to advance the color) : Red, Yellow, Blue, Purple, Green, and then return to clear)

<a name="1001"></a>
### `1001`: Draw line between the center of the cell to the top 

* (add another instance of the code to move the line clockwise)


&rarr; Go back to [List of Codes](#list-of-codes)\
&rarr; Go back to [Index](#index)


## Color

<a name="1010"></a>
### `1010`: Draw a dot in the center of the cell 

around any other features

<a name="1011"></a>
### `1011`: Fill in a quarter of the cell 

around any other features 

(add another instance of the code to move clockwise to the next quarter) 

&rarr; Go back to [List of Codes](#list-of-codes)\
&rarr; Go back to [Index](#index)

<hr>

<a name="sample-programs"></a>
# Sample Programs
