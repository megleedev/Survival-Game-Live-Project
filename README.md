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
For this story I chose a few asset packs listed in the Unreal Marketplace. The first is Deep Elder Caves by Alexander Sychov which contains cave features, mushrooms, statues, rock formations, and flowers. The second is Animal Variety Pack by PROTOFACTOR INC which contains models and animations for five different animals. Using these assets and the Unreal Landscape Tool, I created a basic cave level with a shore and a waterfall leading out of the other side. With moss and water textures from the Starter Content I made the floor of the cave appear damp.<br>

![Screenshot 2023-12-03 021028](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/a1ca3089-dbee-46bc-9f7b-a04e3e71ecf2)
> [!NOTE]
> *Overhead view of the fully built level.*

## Movement and HUD 🏃 
This story began the groundwork for the resource management functionality. After placing the First Person Character and setting the starting position, I created the HUD widget and decided on a design for the resource bars. Ultimately I chose a circular bar to display the player resources so I created a custom material that would gradually decrease as the player took actions in game. <br>

![Screenshot 2023-12-03 021932](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/0789598a-0d6c-4e4c-85be-68b6fbcecc32)
> [!NOTE]
> *Blueprint for the Circular Bar material.* <br>

Once the material was finished I created an instance of it so it could be recolored for each of the player resources and added them to the HUD Canvas Panel: <br>
    🔹Red -  Health <br>
    🔹Green - Stamina <br>
    🔹Orange - Food <br>
    🔹Blue - Water <br>

![Screenshot 2023-12-03 022846](https://github.com/megleedev/Survival-Game-Live-Project/assets/127007134/e6b40a62-5ca4-4dde-aabf-49695fb171d8)
> [!NOTE]
> *Canvas Panel within the HUD Widget.*

## Collectables and Obstacles 🌟
I created AI for the Ghosts by writing a sequence of code that determines the path they can follow and when they pursue the player. First, I used RaycastHit2D to shoot a line from each Node left, right, up, and down so they will be able to find where the Nodes around them are placed. <br>

![image](https://github.com/megleedev/PacMan-Live-Project/assets/127007134/457806b1-b39a-450d-a673-5baa1b0d6c97)
![image](https://github.com/megleedev/PacMan-Live-Project/assets/127007134/10c171c3-a3f2-4d06-babf-483818ca59d5)

Next, I created a function for the AI to determine what direction they can move from the Node they are currently sitting on. Depending on what direction the Nodes are placed around the spot the Ghost is located, the Ghost will decide which direction they can go. <br>

![image](https://github.com/megleedev/PacMan-Live-Project/assets/127007134/ee7fddc0-fd27-4069-af43-7e11ed238e53)

Lastly, the Ghost will begin to pursue the player if it has moved out of the spawn space and into the game space. The Red Ghost begins the game moving out of the spawn space. Pink Ghost and Blue Ghost are on separate timers. <br>

![image](https://github.com/megleedev/PacMan-Live-Project/assets/127007134/f88f2ce9-1a73-4052-9082-2819e5c74b59)
![image](https://github.com/megleedev/PacMan-Live-Project/assets/127007134/b7d41a7b-9a9d-41fc-b66e-bf05d9cb68a4)

***AI In Action***

![](https://github.com/megleedev/PacMan-Live-Project/blob/main/AI_behavior.gif)

This functionality gave me the most trouble by far. I intended to add the Orange Ghost as well but kept having movement issues with it that did not affect the others. I ran out of time to address it so the Orange Ghost was removed from the final product. I suspect that there is a problem with the distance between the Nodes in the spawn area but was in the process of debugging when the Live Project ended. <br>

## Menus ✅ 

As more Ghosts are spawned onto the game board and fewer Nodes remain, player movement was made easier by adding teleportation functionality. To accomplish this, I first added special Nodes to the warp areas on the left and right sides of the game board and deleted the Node sprite so they would appear invisible to the player. Then, I wrote code to determine whether Pac-Man was able to warp.<br>

![image](https://github.com/megleedev/PacMan-Live-Project/assets/127007134/fae0def2-526e-4ca2-a90c-4b91bdd5ee17)

Functionality was also added to allow the Ghosts to warp. <br>

***Warping In Action***

![](https://github.com/megleedev/PacMan-Live-Project/blob/main/Teleport.gif)

The score UI element and functionality was added during this User Story. As in the original game, if a player eats a Node, the score goes up. If the player gets caught by a Ghost, the Lose screen appears and the player has the option to restart the game or return to the Main Menu.

![image](https://github.com/megleedev/PacMan-Live-Project/assets/127007134/185bb22f-bbb6-4fff-90ea-00b82f7b5f2f)

## Complete Gameplay 🎈  

The final tasks on this project were to add the siren background noise and the sound of the Nodes being eaten. <br>

## Lessons Learned 👀

  ⚪ TBD <br>
  ⚪ TBD <br>
  ⚪ TBD <br>
