# Survival Game Live Project

## Introduction 🐣

For two weeks during the C++ and Unreal Live Project - part of The Tech Academy's Game Developer Bootcamp - I was given free reign to design and code my own game in Unreal. I chose to make a Survival game with elements of resource management. Over the course of the Live Project I completed User Stories in five areas: <br><br>
  ✔️ Landscape and Structures <br>
  ✔️ Movement and HUD <br>
  ✔️ Collectables and Obstacles<br>
  ✔️ Menus <br>
  ✔️ Complete Gameplay <br>

Below is a detailed description of the major features and a general description of other functionality implemented during each Story.

## Landscape and Structures 🌅 
For this story I chose a few asset packs listed in the Unreal Marketplace. The first is Deep Elder Caves by Alexander Sychov which contains cave features, mushrooms, statues, rock formations, and flowers. The second is Animal Variety Pack by PROTOFACTOR INC which contains models and animations for five different animals. Using these assets and the Unreal Landscape Tool, I created a basic cave level with a shore and a waterfall leading out of the other side. With moss and water textures from the Starter Content I made the floor of the cave appear covered in moss and damp.<br>

![Screenshot 2023-12-03 021028](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/a1ca3089-dbee-46bc-9f7b-a04e3e71ecf2)
> [!NOTE]
> *Overhead view of the level.*

## Movement and HUD 🏃 
This story began the groundwork for the resource management functionality. After placing the First Person Character and setting the starting position, I created the HUD widget and decided on a design for the resource bars. I thought about adding horizontal bars that would sit in the bottom left corner of the screen, but it looked a bit too cluttered and took up too much area. Ultimately I chose a circular bar to display the player resources so I created a custom material that would gradually decrease as the player took actions in game. <br>

![Screenshot 2023-12-03 021932](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/0789598a-0d6c-4e4c-85be-68b6fbcecc32)
> [!NOTE]
> *Blueprint for the Circular Bar material.* <br>

Once the material was finished I created an instance of it so it could be recolored for each of the player resources and added them to the HUD Canvas Panel. I resized the stat bars depending on their importance as well to make them more visible to the player - Health and Stamina bars were larger and Food and Water bars were smaller: <br>
    🔹Red -  Health <br>
    🔹Green - Stamina <br>
    🔹Orange - Food <br>
    🔹Blue - Water <br>

![Screenshot 2023-12-03 022846](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/e6b40a62-5ca4-4dde-aabf-49695fb171d8)
> [!NOTE]
> *Canvas Panel within the HUD Widget.*

## Collectables and Obstacles 🌟
To add functionality to the Resource Bars, I first created a map of string variables to track each stat. Then I created an Alter Stats function and functions for draining each stat:

![Screenshot 2023-12-04 010737](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/6526d1b1-ea80-4a17-b9fc-0b785d54c6ff)

![Screenshot 2023-12-04 011409](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/bcee0f87-f5fc-4865-86cd-36bbbcb4141b)

![Screenshot 2023-12-04 011432](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/28e5ee3c-3a9a-4131-afdb-b4159e82fbd0)

![Screenshot 2023-12-04 011523](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/bd72f4b6-90b4-4754-96af-1a71cccebea2)

***Resource Bars In Action***

![HUD_ResourceBars](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/97d4ad8a-7854-4c24-9624-d89be7d075c1)

Now that the functionality existed for the Resource Bars to deplete, I added functionality to Replinish them. First I created a Consumable Master blueprint with the basic code that each consumable would need regardless of the stat it refilled. Then I created three copies of the Consumable Master and customized them for each stat. Using the Thirst stat as an example:<br>

![Screenshot 2023-12-13 233648](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/872f2473-705b-4805-a4b5-c5ba40ad3f82)

The player decreases their Thirst Bar (blue) by sprinting. To replinish the stat again, they need to run into the blue sphere. The blue sphere will then spawn again for the player to return to later and refill their Thirst Bar again.<br>

***Thirst Stat Replenish In Action***

![HUD_Consumable](https://github.com/megleedev/Survival-Game-Live-Project/blob/main/HUD_Consumable.gif)

## Menus ✅ 

There are two menus within the game: the Main Menu which includes Play and Quit options and the Pause Menu that is accessable within the game that includes Resume and Quit options.<br>

**Pause Menu**

To access the Pause Menu the player first must be in game. While in game, they press the P button and a transparent light blue overlay with two clickable buttons appears on screen. For this menu functionality it was important that the mouse cursor remained active even though the player wasn't directly interacting with the gameplay. It was also important that the clickable buttons formed a loop from in-game to the Main Menu and back.<br>

![Screenshot 2023-12-13 223844](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/b58ce9d9-a646-4954-9c6b-8870fed83507)

![Screenshot 2023-12-13 223405](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/4a0c7d2d-b4c2-4092-bc00-740e6b8ca7b2)

## Complete Gameplay 🎈  

The final tasks on this project were to add the siren background noise and the sound of the Nodes being eaten. <br>

## Lessons Learned 👀

  ⚪ TBD <br>
  ⚪ TBD <br>
  ⚪ TBD <br>
