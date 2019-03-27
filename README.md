# Abandon
Welcome to the Abandon game project. Called Abandon because that's what happens each time I try to work on it.
Developed using the original Quake Engine; I work on this sporadically in my lunch time.

The aim behind this game is an edgy, dark, first person narrative about whatever I make up as I progress through development.
Do whatever you want with this - fork/rip/alter, I don't care.

If you know a better way of compiling the engine or improving my hacky asset integration process and tool chain please update this readme.

Yes the project structure is complete anarchy, but blame Carmack and crew for that one.

John Romero is God.

## For the Impatient
Invoke WinQuake.exe with args "-game mygame", open terminal, type "map test-compiled" 

## Required Tools
1. MS VS 2008 is required to build the project.
2. TexMex - Create texture wad packs
3. PakExpl - explore PAK0 and PAK1
4. TrenchBroom - Create map files and compile them to BSP

## Build Notes
build gas2masm in debug mode before the winquake project.
if you are getting a "Couldn't load gfx.wad" when you try to run from VS, launch the exe located in Debug directly.

## Running the game
Create a shortcut to the exe inside Debug and invoke the game with "WinQuake.exe -game mygame".
This is a temporary solution; as the project matures we will move away from this.

## Assets
Everything currently lives (will be updated in the future) inside Debug/mygame and Id1.
Quake will first look inside Debug/mygame for assets, then fall back onto Id1

## Maps
Located in Id1/maps
texture wads are loated in maps/extracted
Quake bsp files which contain wads are located in maps/pak_0 and maps/pak_1.
wads need to be extracted from these bsp files with TextMex.
wads should be loaded as a new Texture Collection in TrenchBoom.

To convert a map into a bsp which the Quake engine can use you need to:
1. In TrenchBroom, go Run->Compile then create a new profile
2. Add three tasks.
3. First add the Tool QBSP.exe located in tools/
4. Set the paramters to "{map_name}.map {output_directory}/{name}.bsp" (where output_directory is the maps directory in Id1 or mygame
5. Second add the Tool LIGHT.exe located in tools/
6. Set the parameter to "{output_directory}/{name}.bsp"
7. For the final Task, add the Tool VIS.exe located in tools/
8. Set the parameter to "{output_directory}/{name}.bsp"

To test your map, load Quake, open the console and type "map {map_name}" (you don't need to include the .bsp on the end)

## Resources
If in doubt, check the Quake Wiki: https://quakewiki.org/wiki/Main_Page
