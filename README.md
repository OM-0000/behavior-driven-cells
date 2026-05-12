# behavior-driven-cells
AI cell prototype featuring perception, decision loops, and emergent multi‑agent behavior.

# How to run
1. Install visual studio with the Windows Desktop Development for C++ Suite
2. Download the source code from the src folder
3. Create new windows desktop project in visual studio, empty project
4. In the Solution Explorer, right-click on the project, go to add, existing item and navigate to the source code you downloaded in step 2.
5. Add all the source code to the existing project
6. Use the visual studio compiler to compile the executable
7. Run in the debugger or run the .exe directly

Cells are color-coded based on their state:

green : hungry (seeking food behavior)

red : bored (push mode behavior)

black : observation (experimental)

- Vision "cones" (circle sectors in this version) simulate field of view and are used to calculate the subset of the game world the cells can see, simulating a localized entity.

- Cells have internal states represented by energy. When energy of a cell reaches 70% of its ideal energy level, it enters the hungry state.

- Hungry state triggers foraging behavior where the cell will navigate the map randomly, turning around at the edges of the screen. When it sees a food in the hungry state, it will pursue and eat the food (if possible).

- Bored state triggers similar behavior, but the cell will instead push whatever object it sees. After it executes a push, it observes, logging observed state changes in other objects in its working memory. From this, it calculates a "pushability score" for each object.

- Every object in the world is based on simulated particle physics, including the cells. They navigate by applying force on their bodies using vector math. The basic physics simulation code, along with the game logic is included in this repo.
