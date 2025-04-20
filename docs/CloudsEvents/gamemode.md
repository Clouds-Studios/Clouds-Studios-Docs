---  
weight: 5  
---  

# Game Modes

In this section, we will explain each game mode available in <b>CloudsEvents</b> and their configuration.
!!! info "Assisted Setup"
    The Assisted Setup is a new feature implemented in the plugin that helps configure mini-game maps easily and quickly.
    To enter the Assisted Setup, you need to use a map that hasn't been configured before. Try starting the event, and you will be teleported to the world of the selected map. (There is also a [GUI](gui.md) related to the Assisted Setup, which is mainly used for the "Color Party" mini-game.)
??? inline end "Note"
    You won't be teleported directly to the structure's coordinates. You need to save the coordinates beforehand and put them in the main config file, or you can teleport to them manually.
    Once you’re at the structure, you can start the map Setup, where each section or step will be explained through the chat.<br>


## General Configuration
There is a general configuration section for every game mode that must be set up.

<i>The location where players will spawn when joining the event (X,Y,Z,Yaw,Pitch).</i>  
```yaml title="Coordinates"  
  spawn-location: "0.5,70.0,0.5,0.0,0.0"  
```
<i>The two vertices of the spawn cage (X,Y,Z).</i>  
```yaml title="Cage Coordinates"  
  spawn-cage-pos1: "-5,60,-5"  
  spawn-cage-pos2: "5,65,5"  
```  

<i>The location where players will spawn when the event starts (X,Y,Z,Yaw,Pitch). To disable this (so players will not be teleported), type "disabled".</i> 
```yaml title="Game Spawn"  
  game-spawn-location: "0.5,60.0,0.5,0.0,0.0"  
```  

<i>The Y level for player death.</i>  
```yaml title="Player Death"  
  y-death: 50  
```  

## Color Party 

The <b>Color Party</b> game mode allows you and other players to play with colors. The game <b>randomly</b> selects a color, and you <b>must</b> stand on a block of that color. The last player to fall <b>wins</b>.  

=== "Before the Config"  
    Before configuring the mode, you’ll need to <b>build a map</b> for it.<br><br> 
    <b>How will you do it?</b><br> 
    To do it, you must build a map with a spawn cage and a colored platform below it, including all the colors available in Minecraft.<br>
    
    <i>For example:</i><br> 
    ![ColorPartyMap](https://i.imgur.com/RsDMrdn.png){ align=left }  

=== "After Building"  

    After building the map, we can configure the `mapConfig.yml`. After setting up this configuration section the game mode will be completed.  

    <i>The two vertices of the game base (X,Y,Z).</i>  
    ```yaml title="Vertices of Game base"  
            game-base-pos1: "25,60,25"  
            game-base-pos2: "-25,60,-25"  
    ```  

    <i>The blocks used in the game base. Available blocks: wool, terracotta, concrete.</i>  
    ```yaml title="Color of blocks"  
            color-block: "wool"  
    ```  

    <i>The level from which PvP will be enabled. To disable it, type -1.</i>  
    ```yaml title="Level of PvP enabled"  
            pvp-level: 10  
    ```  

    <i>The PvP type. If multiple, separate them with `;;`</i>  
    - <i>HAND (fist combat)</i><br>
    - <i>SNOWBALL</i>

    ```yaml title="PvP type"  
            pvp-type: "HAND;;SNOWBALL"  
    ```  

    <i>The hotbar position for snowballs (1-9).</i> 
    ```yaml title="Snowball position"  
            snowball-hotbar: 9  
    ```  

    <i>Levels section (level: seconds).</i>  
    ```yaml title="Level countdown"  
            levels:  
              1: 5  
              3: 4  
              5: 3  
              10: 2  
    ```  

    And this is how you can configure the ColorParty mode.  

## Sumo FFA  
The Sumo FFA mode consists of PvP without weapons. The last player to fall <b>wins</b>.  

=== "Before the Config"  
    Before configuring it, as in ColorParty, you need a map with a spawn cage and a platform below where players can fight.<br> 

    <i>For example:</i><br>
    ![SumoFFAMap](https://i.imgur.com/WSsb7WU.png){ align=left }  

=== "After Building"  
    <i>In this mode, there is no a specific configuration. Unlike the previous one, you only need to fill in the general configuration.</i>

## Timer Spleef  
The <b>Timer Spleef</b> game mode consists of multiple platforms where, if a player touches a block, it gradually changes color until it <b>disappears</b>. The last player to fall <b>wins</b>.  

=== "Before the Config"  
    Before configuring it, as in the previous game modes, you'll build a map. There will be a spawn cage, but instead of a colored platform, there will be multiple platforms made of a specific block, stacked one below the other.<br> 

    <i>For example:</i><br>  
    ![TimerSpleefMap](https://i.imgur.com/rryGfk5.png){ align=left }  

=== "After Building"  
    <i>The blocks in the different levels. Use the server version Material API (level: "material") [For legacy versions, use Material:Data].</i>  
    ```yaml title="Blocks Level"  
            blocks-level:  
            0: "WOOL:0"  
            1: "WOOL:4"  
            2: "WOOL:1"  
            3: "WOOL:14"  
    ```  

    <i>The seconds between each level.</i>  
    ```yaml title="Seconds"  
            level-time: 5  
    ```
## Anvil Rain 
Anvil Rain is a game mode that literally consists of a rain of anvils, gradually increasing in intensity as more and more anvils fall. The winner is the one who manages to survive the longest under this anvil storm

=== "Before the Config"  
    Before configuring it, a map is required. To build it, you only need a platform made of any block and a spawn cage. The map itself should be surrounded by walls to prevent players from falling off the edge of the world.

    <i>For example:</i><br>
    ![AnvilRainMap](https://i.imgur.com/iA0xUdw.png){ align=left }

=== "After Building"
    <i>The two vertices of the game base (X,Y,Z).</i>
        ```yaml title="Vertices Position"
                ar-game-base-pos1: "64,64,0"
                ar-game-base-pos2: "0,64,-69"
        ```
    <i>The milliseconds when the first anvil spawns.</i>
        ```yaml title="Milliseconds"
                starting-milliseconds: 3000
        ```
    <i>The leniency settings for the game mode.</i>
        ```yaml title="Leniency"
              time-leniency: 5
              block-leniency: 3  
        ```