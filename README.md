<div align="center">  

![Bannero](./bannersgithub.gif)
<del>*Join to the discord for more info*</del>

[![Discord](https://img.shields.io/badge/Discord-%235865F2.svg?style=for-the-badge&logo=discord&logoColor=white&color=FF0000)](https://discord.com/invite/JCjwNgZgsp)
</div>  
  
 ### A Minecraft plugin that enables the detection of keys.


**Main Features**

**1. Movement-Based Menu System**  

 Players can interact with menus by moving in different directions using his keyboard <br>
 *(forward, backward, left, right, jump, or crouch).* <br>
 Automatic menu transition when players reach the target coordinates.  
 You can close the menu sprinting (ctrl)

   
![Plugin demo](./plugindemo.gif)

#### **2. Flexible Multi-Access Menu Configuration**  
 Each menu can have multiple access points, allowing for diverse player interactions.  
 Example configuration:  
```yaml
default:
  enabledCoordinates:
    1:
      from:
        x: 0
        y: 1
        z: 0
      to:
        x: 8
        y: 1
        z: 0
    2:
      from:
        x: 1
        y: -1
        z: 0
      to:
        x: 8
        y: -1
        z: 0
  '1':
    targetX: 5
    targetY: 1
    targetZ: 1
    command: /say hello %player%
    executionType: op # Can be as console/player/op
  '2':
    targetX: 5
    targetY: 1
    targetZ: 0
    nextMenu: menuthree #name of the menu if you meet this coords
  '3':
    targetX: 1
    targetY: 1
    targetZ: 0
    nextMenu: menuthree
    command: /say hello %player%
    executionType: player
menuthree:
  blockedCoordinates:
    from:
      x: 0
      y: 1
      z: 0
    to:
      x: 8
      y: 1
      z: 0
  '1':
    targetX: 7
    targetY: 5
    targetZ: 1
    nextMenu: default
    command: /say hello %player%
    executionType: console
```
**3. In-Game Reload Command**
- /reloadmenus: Reloads the menus directly in-game, applying any changes made in the config.yml file without restarting the server.

**4. Simple and Powerful Commands**
- /startmenu: Starts the default menu for the player.
- /modifymenu (name) (transition point) (coordinates) (next_menu)/(command) (sender): Adds or modifies a menu with its target coordinates and transition logic.
- Examples:
  - /modifymenu default 1 x5y1z1 "/say hello %player%" op #adding a command to x5y1z1
  - /modifymenu default 2 x5y1z0 menuthree # adding a new menu to x5y1z0
  - /modifymenu default 3 x1y1z0 menuthree "/say hello %player%" op #adding a command and a next menu to x1y1z0

**5. Persistent Storage**
All menu configurations are stored in config.yml and persist through server restarts.

**6. Real-Time Interaction**
Menus automatically switch when players reach the target.

**7. Player Personalization**
Each player has an independent menu state, allowing for customized interactions and progress.

**8. Player Freezing and Unfreezing**
Players are "frozen" (movement disabled) while interacting with menus.
Movement speed is automatically restored when menus are closed.

**10. Multi-Access Points for Menus**
Each menu supports multiple access points, providing flexibility for complex menu flows.
