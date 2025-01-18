# maCart
_Code yourself some **ma**caroni **art** with **C**-shaped pasta._
###### last updated: January 17, 2025

[Index](#index)
* [About](#about)
  * What is macaroni art?

* [maCart Basics](#macart-basics)
  * A single macaronus
  * Starting positions
  * Always clockwise...
  * ...Using design clocks

* [Command List](#command-list)
  * Macaronus
  * Arrange
  * Art
  * Advanced Art

* [Examples](#examples)

* [Inspiration](#inspiration)
  * Real-life macaroni art
  * Other related macaroni art 

# [About]
#### What is macaroni art?

_TK_

&rarr; Go back to [Index]

## [maCart Basics]
#### A single macaronus

For our purposes, a single piece of digital macaroni art drawn with this program is called a "maCart drawing", and the basic unit of a maCart drawing is a "macaronus": a 4-cell, diamond-shaped grid, where each cell can either have a piece of pasta added or skipped and left empty. Each piece of pasta, as it's placed, can be flipped, rotated, have smaller or larger shadows of varying levels of transparency and either along the convex or concave side.

Examples: 

_TK_ 

maCart drawings are composed of one or more macaronus units, allowing for very small and simple digital pieces mimicking children's compositions or for infinite-canvas mosaics.

#### Starting positions

* The macaronus starts empty (blank).

Example: _TK_

* The basic pasta shape is "macaroni".

Example: _TK_

* The first macaroni placed in the macaronus always starts in the upper-left corner. Subsequent macaroni are placed clockwise until the macaronus is filled, but macaroni can continue to be layered over one another until a new macaronus is added to the maCart drawing.

Example: _TK_

* Macaroni always start "C" shaped in its cell. Additional commands can be given to manipulate the macaroni until a new macaroni is added to the next cell.

Example: _TK_

* Colors can be changed through different commands, but don't have to be.
  * The macaroni is yellow.
  * The lighting on the macaroni is coming from directly above, with no shadows (i.e., 100% transparent).
  * The background color of the macaronus starts as "kraft" (cardboard).
  * The implied "glue" that creates a macaronus perfectly aligned with the pasta (i.e., 100% transparent).

Example: _TK_

#### Always clockwise...

When composing a maCart drawing, the macaronus starts in the center of the digital canvas--and just as a macaronus is composed clockwise starting from the upper-left, so too are maCart drawings composed of new macaronus units added in a clockwise spiral around the central macaronus. Every new macaroni, and every new macaronus, starts on the upper left of the "clock".

Example: _TK_

Each new macaroni can be rotated be rotated clockwise as well, on either a macro or micro level.

Example: _TK_

While the macaroni can be layered, the macaronus units spiral out as they get added on. If you imagine each side of the macaronus labeled with letters (again, starting clockwise from the upper-left), a macaronus would look like this:

Example: _TK_

Each new macaronus is added so that one side is aligned to specific side of the previous, starting from the upper-left and circling clockwise. The pattern is:

AC(1), BD(1), CA(2), DB(2), AC(3), BD(3), CA(4), DB(4), AC(5), BD(5)...

Example: _TK_

#### ...Using design clocks

Imagining clocks (and clockwise movement) helps minimize the number of commands needed to implement a lot of different options without having to waste additional commands to individually label specific settings.

* Color clock

Example: _TK_

* Light clock
  
Example: _TK_

* Shadow clock
  
Example: _TK_

* Glue clock

Example: _TK_

&rarr; Go back to [Index]

# [Command List]
#### Macaronus

0000 - Makes a new macaronus on the canvas

1000 - Add a macaroni to the current cell

0100 - Move to next cell in macaronus

#### Arrange

1001 - Flip macaroni on its vertical axis

0111 - Macro rotate macaroni (clockwise 90 degrees)

0001 - Micro rotate macaroni (clockwise 24 degrees)

#### Art

0011 - Changes the color of the macaronus's construction paper by advancing the "color clock" once for each command (Kraft Red Yellow Blue Black White)

1101 - Increases the size of the macaroni's shadow by advancing the "light clock" once for each command (0% larger than macaroni, 25% larger, 50% larger, 75% larger)

1011 - Increases the opacity of the macaroni's shadow by advancing the "shadow clock" once for each command (25% transparency black, 50% transparency black, 75% transparency black, 100% transparency black)

0101 - Shift the shadow from the convex side of the macaroni to the concave

#### Advanced Art

1100 - Changes glue color by advancing the "glue clock" once for each command (White Red Yellow Blue Purple at 15% transparency, White at 100% transparency)

1111 - Pasta size (1 macaroni fills entire macaronus, can be used instead of 00 but overwrites any use of the 000 arrangement command)

0110 - Copy previous macaronus (overwriting any previous copied macaronus)

1010 - Paste copied macaronus

&rarr; Go back to [Index]

## [Examples]

_TK_

&rarr; Go back to [Index]

## [Inspiration]
#### Real-life macaroni art

_TK_

#### Other related macaroni art 

_TK_

&rarr; Go back to [Index]
