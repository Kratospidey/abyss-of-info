---
{"dg-publish":true,"permalink":"/college/sem-iv/physics/pgr/pgr-computational-details/"}
---

## Software Details

- Language used - C#
-  Framework Used - .NET 5.0
- Libraries used - SFLM.NET,  Big Gustave
## Markdown table

| Property | Explanation |
|----------|-------------|
| Gravity | The force of gravity, expressed as a float value |
| OneEighthOfGravity | One-eighth of the Gravity value |
| MethaneGravity | Two times the negative of Gravity value |
| GasGravity | Negative of Gravity value |
| MaxRadius | The maximum radius of an object, expressed as an integer value |
| WaterSpreadRate | The rate at which water spreads, expressed as an integer value |
| SandSpreadRate | The rate at which sand spreads, expressed as an integer value |
| OilSpreadRate | The rate at which oil spreads, expressed as an integer value |
| AcidSpreadRate | The rate at which acid spreads, expressed as an integer value |
| LavaSpreadRate | The rate at which lava spreads, expressed as an integer value |
| MethaneSpreadRate | The rate at which methane spreads, expressed as an integer value |
| FireSpreadChance | The chance of fire spreading, expressed as an integer value (1.0/chance) |
| BurningGasSpreadChance | The chance of burning gas spreading, expressed as an integer value (1.0/chance) |
| SteamSpreadSpeed | The speed at which steam spreads, expressed as a float value |
| SmokeSpreadSpeed | The speed at which smoke spreads, expressed as a float value |
| FireLifeTime | The lifetime of fire in frames, expressed as an integer value |
| SteamLifeTime | The lifetime of steam in frames, expressed as an integer value |
| SmokeLifeTime | The lifetime of smoke in frames, expressed as an integer value |
| EmberLifeTime | The lifetime of embers in frames, expressed as an integer value |
| LavaLifeTime | The lifetime of lava in frames, expressed as an integer value |
| BurningGasLifeTime | The lifetime of burning gas in frames, expressed as an integer value |
| VirusLifeTime | The lifetime of virus in frames, expressed as an integer value |
| SmokeSpawnChance | The chance of smoke spawning, expressed as an integer value (1.0/chance) |
| SteamSpawnChance | The chance of steam spawning, expressed as an integer value (1.0/chance) |
| EmberSpawnChance | The chance of embers spawning, expressed as an integer value (1.0/chance) |
| AshSpawnChance | The chance of ash spawning, expressed as an integer value (1.0/chance) |
| LavaSpawnsSmokeChance | The chance of lava spawning smoke, expressed as an integer value (1.0/chance) |
| LavaSpawnsEmberChance | The chance of lava spawning embers, expressed as an integer value (1.0/chance) |
| SteamCondencesChance | The chance of steam condensing, expressed as an integer value (1.0/chance) |
| SmokeCondencesChance | The chance of smoke condensing, expressed as an integer value (1.0/chance) |
| LavaMeltsStoneChance | The chance of lava melting stone, expressed as an integer value (1.0/chance) |
| LavaMeltsSandChance | The chance of lava melting sand, expressed as an integer value (1.0/chance) |
| LavaMeltsDirtChance | The chance of lava melting dirt, expressed as an integer value (1.0/chance) |
| WoodIgnitionChance | The chance of wood igniting, expressed as an integer value (1

## Code Snippet explanation

here's a short explanation of a few individual critical functions used in the code

1.  `Swap`: This method swaps two particle elements in the matrix and updates their colors.
2.  `StepAll`: This method performs a step function on all particles in the matrix, which updates their position and velocity based on the laws of physics. 
3.  `Add`: This method adds a particle to the matrix at a specified position with a specified velocity, or at a specified position without a velocity.
4.  `Erase`: This method removes a particle from the matrix.
5.  `Set`: This method sets the type of a particle in the matrix.
6.  `ToggleFrameUpdate`: This method toggles the frame update of the matrix, which is used to keep track of which elements have been updated in the current frame.
7.  `GetMatrix`: This method returns the matrix representation of the particle system.

## Explanation of the ArrayExtension.cs file

The code is a .NET class named "ArrayExtensions" that extends the functionality of arrays in C#. It contains two methods "Fill" for arrays and 2D arrays, both having the same functionality.

The method checks if the destination array is null and throws an `ArgumentNullException` if it is. It then checks if the length of the value array is more than the length of the destination array and throws an `ArgumentException` if it is.

Then, it sets the initial value of the destination array using the `Array.Copy` method, which is a built-in method to copy the elements of one array to another. The method then copies the initial value to the destination array multiple times until the length of the destination array is filled.

The 2D array "Fill" method works in the same way as the 1D array "Fill" method.

## Explanation of the World.cs file

The code is for a class `World` in a simulation sandbox using the SFML graphics library in C#. The class has properties `Width` and `Height` that determine the size of the canvas, `SelectionRadius`, `SelectedMaterial`, `FPS`, and `IsUsed` that track the state of the simulation. The class also has methods to interact with the simulation such as `Clear`, `Load`, `GetMatrix`, `Draw`, `Update`, `StartInput`, `StopInput`, and `UpdateMousePosition`. The simulation logic is maintained by the `CellularMatrix` class, which holds a two-dimensional array of `MaterialType` and updates its state based on its own rules, triggering an update to the `ImageArray` class, which holds an array of pixels that represent the current state of the simulation on the canvas. The canvas is drawn on the screen with a sprite and a fragment shader that can be applied to it. The class also tracks the frames per second (FPS) of the simulation.


## Explanation of Program.cs file

This is the `Main` method of a C# program using the SFML library for graphics and windowing. The purpose of this program is to create a sandbox simulation in which a user can interact with different materials (such as sand) and perform different actions like painting, clearing, saving, and loading the simulation.

The `Main` method first sets the thread priority to the highest and initializes the window size, world simulation, and UI. Then, it sets up event listeners for mouse and keyboard interactions. The main loop of the program then dispatches events, updates the world simulation if it's running, draws the world and UI, and updates the window title with the current FPS and milliseconds per frame.

## Explanation of Util.cs File

This code defines a `Utils` static class in the `SandBoxSFML` namespace. The class provides several utility functions that manipulate numbers, colors and random values. These functions are:

1.  `Clamp(int num, int min, int max)` - clamps an integer value `num` between a given minimum and maximum value.
2.  `Next(int min, int max)` - returns a random integer between a given minimum and maximum value.
3.  `NextDouble()` - returns a random floating-point number between 0 and 1.
4.  `RandomValue(int lower, int upper)` - returns a random integer between two given bounds, swapping the bounds if `lower` is greater than `upper`.
5.  `NextBoolean()` - returns a random boolean value, either `true` or `false`.
6.  `InvertColor(Color color)` - inverts an RGB color by subtracting each of its color values (R, G, B) from 255, and returning a new color.

The code also uses `System` and `SFML.Graphics` namespaces, and creates a private static `Random` object `_r` for generating random values.


The link for the Whole Codebase is at - https://github.com/Kratospidey/pps



