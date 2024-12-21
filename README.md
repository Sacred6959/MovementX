# MovementX
A Minecraft plugin that enables movement-based menus

 **Main Features of the MovementMenu Plugin**

**1. Movement-Based Menu System**  
- Players can interact with menus by moving in different directions using his keyboard (forward, backward, left, right, jump, or crouch).  
- Automatic menu transition when players reach the target coordinates.  
- You can close the menu sprinting (ctrl)
#### **2. Flexible Multi-Access Menu Configuration**  
- Each menu can have multiple access points, allowing for diverse player interactions.  
- Example configuration:  
```yaml
default:
  1:
    targetX: 1
    targetY: 1
    targetZ: 0
    nextMenu: menutwo
  2:
    targetX: 5
    targetY: 1
    targetZ: 0
    nextMenu: menuthree
menutwo:
  1:
    targetX: 1
    targetY: 1
    targetZ: 0
    nextMenu: default
  2:
    targetX: 5
    targetY: 1
    targetZ: 0
    nextMenu: menuthree
```
**3. In-Game Reload Command**
- /reloadmenus: Reloads the menus directly in-game, applying any changes made in the config.yml file without restarting the server.

**4. Simple and Powerful Commands**
- /startmenu: Starts the default menu for the player.
- /modifymenu (name) (coordinates) (next_menu): Adds or modifies a menu with its target coordinates and transition logic.

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
