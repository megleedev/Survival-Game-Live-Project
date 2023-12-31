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
For this Story I chose a few asset packs listed in the Unreal Marketplace. The first is Deep Elder Caves by Alexander Sychov which contains cave features, mushrooms, statues, rock formations, and flowers. The second is Animal Variety Pack by PROTOFACTOR INC which contains models and animations for five different animals. Using these assets and the Unreal Landscape Tool, I created a basic cave level with a shore and a waterfall leading out of the other side. With textures from the Starter Content I made the floor of the cave appear covered in moss and damp.<br>

![Screenshot 2023-12-03 021028](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/a1ca3089-dbee-46bc-9f7b-a04e3e71ecf2)
> [!NOTE]
> *Overhead view of the level.*

## Movement and HUD 🏃 
This Story began the groundwork for the resource management functionality. After placing the First Person Character and setting the starting position, I created the HUD widget and decided on a design for the Resource Bars. I thought about adding horizontal bars that would sit in the bottom left corner of the screen, but it looked a bit too cluttered and took up too much area. Ultimately I chose a circular bar to display the player stats so I created a custom material that would gradually decrease as the player took actions in game. <br>

![Screenshot 2023-12-03 021932](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/0789598a-0d6c-4e4c-85be-68b6fbcecc32)
> [!NOTE]
> *Blueprint for the Circular Bar material.* <br>

Once the material was finished I created an instance of it so it could be recolored for each of the player stats and added them to the HUD Canvas Panel. I resized the stat bars depending on their importance as well to make them more visible to the player - Health and Stamina bars are larger and Food and Water bars are smaller: <br>
    🔹Red -  Health <br>
    🔹Green - Stamina <br>
    🔹Orange - Food <br>
    🔹Blue - Water <br>

![Screenshot 2023-12-03 022846](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/e6b40a62-5ca4-4dde-aabf-49695fb171d8)
> [!NOTE]
> *Canvas Panel within the HUD Widget displaying the four player stats.*

## Collectables and Obstacles 🌟
To add functionality to the Resource Bars, I first created a map of string variables to track each stat. Then I created an Alter Stats function and functions for draining each stat:

![Screenshot 2023-12-04 010737](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/6526d1b1-ea80-4a17-b9fc-0b785d54c6ff)

![Screenshot 2023-12-04 011409](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/bcee0f87-f5fc-4865-86cd-36bbbcb4141b)

![Screenshot 2023-12-04 011432](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/28e5ee3c-3a9a-4131-afdb-b4159e82fbd0)

![Screenshot 2023-12-04 011523](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/bd72f4b6-90b4-4754-96af-1a71cccebea2)

***Resource Bars In Action***

![HUD_ResourceBars](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/97d4ad8a-7854-4c24-9624-d89be7d075c1)

Now that the functionality existed for the Resource Bars to deplete, I added functionality to replenish them. First I created a Consumable Master blueprint with the basic code that each consumable would need regardless of the stat it refilled. Then I created three copies of the Consumable Master and customized them for each stat. Using the Thirst stat as an example:<br>

![Screenshot 2023-12-13 233648](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/872f2473-705b-4805-a4b5-c5ba40ad3f82)

The player decreases their Thirst Bar (blue) by sprinting. To replenish the stat again, they need to run into the blue sphere. The blue sphere will then spawn again for the player to return to later and refill their Thirst Bar again.<br>

***Thirst Stat Replenish In Action***

![HUD_Consumable](https://github.com/megleedev/Survival-Game-Live-Project/blob/main/HUD_Consumable.gif)

## Menus ✅ 

There are two menus within the game: the Main Menu which includes Play and Quit options and the Pause Menu that is accessible within the game and includes Resume and Quit options.<br>

To access the Pause Menu the player first must be in game. While in game, they press the P button and a transparent light blue overlay with two clickable buttons appears on screen. For this menu functionality it was important that the mouse cursor remained active even though the player wasn't directly interacting with the gameplay. It was also important that the clickable buttons formed a loop from in-game to the Main Menu and back.<br>

![Screenshot 2023-12-13 223844](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/b58ce9d9-a646-4954-9c6b-8870fed83507)

![Screenshot 2023-12-13 223405](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/e0b7ab59-c98d-4a01-81f9-ffa4d6249824)
> [!NOTE]
> *In-game Pause Menu.*

![Screenshot 2023-12-14 011449](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/5854c505-0e58-49ce-840f-67167fb00b32)
> [!NOTE]
> *Front-end Main Menu.*


## Complete Gameplay 🎈  

The last aspect of the game I had the time to complete was the enemy AI. For this I started with the Wolf. I added a Pawn sensing component that would give the Wolf the ability to hear (blue wiring) and see (green wiring) the player. I did some adjustments to the range for both of those sensors to make sure they weren't too close or too far. Then I added two Arrow components that would draw lines in the direction the Wolf is facing and start their attack if they detect the player. <br>

![Screenshot 2023-12-14 001106](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/ed0d7ff0-c44b-4ee9-a230-9bf590730a9a)
> [!NOTE]
> *Wolf with added components.*

Then I started working on the Enemy AI. The enemy has three behaviors: Roaming, Following, Attacking.

![Screenshot 2023-12-14 003614](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/54096672-de1b-43cd-bc9f-aa732cc67f41)
> [!NOTE]
> *Roaming is the default behavior. The enemy has not detected the player and is performing a basic walk cycle to random points on a radius that covers the map.*

![Screenshot 2023-12-14 004225](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/5d5632d1-f8d9-4677-a3be-381d1e70fb20)
> [!NOTE]
> *Following is the behavior that occurs when the player moves into the enemy's hearing or sight range. It begins to run after the player and will follow them around until they move out of the enemy's range again.*

![Screenshot 2023-12-14 004420](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/5c3432d2-0178-4e44-b17f-fb575d16185a)
> [!NOTE]
> *Attacking is the behavior that occurs when the enemy catches up to the player and the player is detected by the arrow components drawing lines in front of it. Attacks cause damage to the player and affects their Health stat.*

***AI Behavior In Action***

![AI_Behavior](https://github.com/megleedev/Survival-Game-Live-Project/blob/main/AI_Behavior.gif)


## Lessons Learned 👀

  ⚪ Rather than using a map to track the various player stats, I should have created them as individual variables. That would have made them easier to reference and use within the various systems I designed. <br><br>
  ⚪ I learned after I had already hardcoded the AI that there was an Unreal system for the exact functionality I was trying to implement called Behavior Trees. Using Behavior Trees would have been much more efficient and easier to work with.<br><br>
  ⚪ A different setting would have actually been better for this game. Exploring a cave implies no/low light. I sculpted a roof for the existing level but realized I would need to spend time lighting the area if I used it so it now exists in the world outside of camera view so the player can see the environment. A forest or beach setting would have been better for what I was trying to do.<br><br>
