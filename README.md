# smc_cppserial_lib
This is a child project of the Samuko Motor Control (SMC) project. This library can be used in your linux cpp robotic project (as it depends on the libserial-dev package) to communicate with the **`smc_l298n_pid_driver module`** in order to send target angular velocities to the motors or receive the motor's angular velocity and angular position, after successful velocity PID setup with the [**`smc_app`**](https://github.com/samuko-things-company/smc_app).

> you can use it in your microcomputer robotics project **running on linux** (e.g Raspberry Pi, PC, etc.)

A simple way to get started is simply to try out and follow the example code in the example folder


## How to Use the Library
- install the libserial-dev package
  > sudo apt-get update
  >
  > sudo apt install libserial-dev

- Ensure you have the **`smc_l298n_pid_driver module`** interfaced with your preferred motors, setup the encoder and PID parameters with the **`smc_app`**.

- Download (by clicking on the green Code button above) or clone the repo into your PC.

- A simple way to get started is simply to try out and follow the example code.

- make, build and run the example code.
  > cd into the root directory
  >
  > mkdir build (i.e create a folder named build)
  >
  > enter the following command in the terminal in the root folder:
    ````
    cmake -B ./build/
    ````
    ````
    cmake --build ./build/
    ````
    ````
    ./build/example_control_code
    ````

- You can follow the pattern used in the example in your own code.


## Basic Library functions and usage

- connect to **smc_l298n_pid_driver shield** module
  > .connect("port_name or port_path")

- send target angular velocity command
  > .sendTargetVel(motorA_TargetVel, motorB_TargetVel)

- send PWM commands
  > .sendPwm(motorA_PWM, motorB_PWM)

- read motors angular position
  > .getMotorsPos(&angPosA, &angPosB) // copies the motors angular position into angPosA, angPosB

- read motors angular velocity
  > .getMotorsVel(&angVelA, &angVelB) // copies the motors ang vel angVelA, angVelB
