# Ex.No:3(D)    INTERFACE 

## QUESTION:

You’re developing a multi-console gaming platform that supports different controllers. Each controller has its own way of mapping buttons for actions like Jump, Shoot, and Pause.

To unify this behavior, you're asked to design a system using Java Interfaces. The interface will standardize the controls, and each controller will implement them differently.

Your Task: Create an interface GameController with methods:

jump() shoot() pause() Implement three controller types:

PlayBoxController XCubeController RetroFunController

## AIM:

To design a unified controller system using Java Interfaces where different gaming consoles implement their own button mappings for actions like Jump, Shoot, and Pause.

## ALGORITHM :

Define an interface GameController with methods :jump(),shoot(),pause()

Create class PlayBoxController implementing the interface and defining console-specific button actions.

Create class XCubeController implementing the interface with its own button mapping.

Create class RetroFunController implementing the interface using classic button controls.

Create one controller object at a time.

Call the three methods (jump, shoot, pause) to demonstrate polymorphism.



## PROGRAM:
 ```
/*
Program to implement a Interface using Java
Developed by: HarrishVenkat V
RegisterNumber: 212223240049
*/
```

## SOURCE CODE:


import java.util.*;

interface GameController {
    void jump();
    void shoot();
    void pause();
}

class PlayBoxController implements GameController {
    public void jump() {
        System.out.println("PlayBox: Press X to Jump!");
    }
    public void shoot() {
        System.out.println("PlayBox: Press R2 to Shoot!");
    }
    public void pause() {
        System.out.println("PlayBox: Press Start to Pause.");
    }
}

class XCubeController implements GameController {
    public void jump() {
        System.out.println("X-Cube: Press A to Jump!");
    }
    public void shoot() {
        System.out.println("X-Cube: Press RT to Shoot!");
    }
    public void pause() {
        System.out.println("X-Cube: Press Menu to Pause.");
    }
}

class RetroFunController implements GameController {
    public void jump() {
        System.out.println("RetroFun: Use Up Arrow to Jump!");
    }
    public void shoot() {
        System.out.println("RetroFun: Press B to Shoot!");
    }
    public void pause() {
        System.out.println("RetroFun: Press P to Pause.");
    }
}

public class GameInputSimulator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String controllerType = sc.nextLine().toLowerCase();
        String action = sc.nextLine().toLowerCase();

        GameController controller;

        switch (controllerType) {
            case "playbox":
                controller = new PlayBoxController();
                break;
            case "xcube":
                controller = new XCubeController();
                break;
            case "retro":
                controller = new RetroFunController();
                break;
            default:
                System.out.println("Unsupported controller!");
                return;
        }

        switch (action) {
            case "jump":
                controller.jump();
                break;
            case "shoot":
                controller.shoot();
                break;
            case "pause":
                controller.pause();
                break;
            default:
                System.out.println("Unknown action!");
        }
    }
}





## OUTPUT:

<img width="911" height="290" alt="image" src="https://github.com/user-attachments/assets/bcc5c23f-44ff-4802-aea2-84e2acfdbfb4" />


## RESULT:
Therefore the program successfully unifies different gaming controllers using a common interface.

