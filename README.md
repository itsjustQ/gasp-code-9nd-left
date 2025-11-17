# GASP Code 9nd Left

This repository contains a VEX V5 C++ project used to control a VEX robotics platform with two left drive motors, two right drive motors, and an intake system. The code includes both autonomous and driver-controlled routines.

## Features

- Four-drive-motor tank drive configuration (two motors per side) configured with a 18:1 gear ratio.
- Big and small intake motors for handling game objects.
- Autonomous routine that moves the robot forward and backward, turns, and operates the intake motors.
- Driver control functions that map joystick axes for forward/reverse movement and turning, and map controller buttons to operate intake/output motors.
- Generates a random seed based on battery current, voltage, and system time (though not used in current logic).

## Getting Started

This project is provided as a `.v5cpp` file (`GASP_Code_9nd Left.v5cpp`). The `.v5cpp` format is a VEXcode V5 C/C++ project archive. To import and build this project in your development environment, you can use the VEX Visual Studio Code extension or VEXcode V5.

### Importing the project in the VEX VS Code Extension

1. Install the VEX VS Code extension and open VS Code.
2. In the VEX activity bar, select **Import Project** under **Project Actions**.
3. When prompted, choose the `.v5cpp` file. The VEX library notes that supported V5 project file types include `.v5cpp` for C/C++ projects.
4. Provide a project name, description, and location when prompted; you can keep the default values.
5. Once imported, open `src/main.cpp` to view or modify the code. Connect your V5 Brain and use the extension to build and download the program to your robot.

### Importing the project in VEXcode V5

If you are using the VEXcode V5 application (desktop or web):

1. Launch VEXcode V5.
2. Choose **Import** from the project selector and select the `.v5cpp` file.
3. VEXcode will create a new project with the same name and load the code. You can then build and download the program to a connected V5 Brain.

## Autonomous Routine

The `runOnAutonomous()` function sets motor velocities and executes a sequence of `spinFor()` calls to drive the robot forward and backward and turn by spinning opposing motors. It also runs the intake motors at specific points in the routine.

## Driver Control

The driver control loop reads values from **Axis3** (forward/backward) and **Axis1** (turning) on Controller1 to update state flags (`driveForward`, `driveBackward`, `turnLeft`, and `turnRight`). Buttons **R1** and **R2** control intake and output modes. The `robotActions()` function uses these flags to spin the drive and intake motors accordingly.

## License

This project is shared for educational purposes. You are welcome to modify and use this code for your VEX robotics projects. No specific license is provided.
