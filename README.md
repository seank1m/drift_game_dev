# Car Controller - Drift Game & Personal C# Exploration Project
## Introduction
This project is a personal endeavor to explore and enhance my understanding of the C# programming language, particularly within the context of game development using Unity and Object Oriented Programming. The primary goal is to create a simple car controller that simulates basic car physics, including acceleration, steering, drag, and traction.
## Project Overview

The project consists of a Unity script that controls a car's movement. Key features include:

- **Acceleration and Deceleration**: Using user input to increase and decrease the car's speed.
- **Steering**: Allowing the car to turn left and right based on user input.
- **Drag**: Simulating friction to slow the car down over time.
- **Traction**: Controlling how the car's movement direction aligns with its forward direction.

## Script Explanation

The core of the project is the `CarController` script, written in C#. Below is a detailed breakdown of the script's functionality:

### Variables

- **MovingSpeed**: Controls the rate of acceleration.
- **DragConstant**: Represents the drag coefficient, slowing down the car over time.
- **MaxSpeed**: Caps the car's maximum speed.
- **SteeringAngle**: Determines the angle at which the car steers.
- **Traction**: Adjusts how quickly the car's movement direction aligns with its forward direction.
- **MovingForce**: The current velocity of the car.

### Methods

#### Update()

This method is called once per frame and handles the car's movement and steering.

1. **Acceleration and Movement**:
    - Calculates the forward force based on user input and adds it to `MovingForce`.
    - Updates the car's position based on `MovingForce`.
    - Applies drag to gradually reduce `MovingForce`.
    - Clamps `MovingForce` to ensure it does not exceed `MaxSpeed`.

2. **Steering**:
    - Adjusts the car's rotation based on user input and the current speed.

3. **Traction**:
    - Gradually aligns `MovingForce` with the car's forward direction.

### Debugging

The script includes debug lines to visualize the car's movement and direction in the Unity Editor's Scene view:

- **Green Line**: Indicates the direction and magnitude of `MovingForce`.
- **Blue Line**: Represents the car's forward direction.

## Demo 
[!Starting Position] (img src="./images/start.PNG"/)
