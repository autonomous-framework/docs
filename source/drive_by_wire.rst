
Drive By Wire
-------------

Design
------

.. contents:: Table of contents
    :depth: 2
    :local:

This document describes the design of the drive by wire system used in the Autonomous Rover.

Overwiew
--------

The goal of a drive by wire system is to enable the control of a vehicle using a computer. It is considered the heart of advanced driver assisiance systems (ADAS) and autonomous vehciles applications. It enables the implementation of a wide range of applications in the automotive field. Typically, the system is composed of one or more compute platforms and a set of sensors and actuators. The system is then installed onto a vehicle to enable the control of the throttle, the brakes and the steering wheel. Each one of those components is categorized as a subsystem of the overall drive-by-wire system.

In the Autonomous Rover application, the steering wheel and the throttle are controllable through an Electronic Speed Controller (ESC), which accepts an PWM signal with a duty cycle between 1ms and 2ms, with 1.5ms being the center or the zero position. The ESC accepts a PWM frequency in the range of 100Hz.

An Electronic Control Unit (ECU) will need to be programmed to send the PWM output the the ESC in order to control the vehicle velocity and direction.

In this project a Tiva C, TM4C123GXL, microcontroller (MCU) has been chosen as the drive-by-wire ECU since it contains all the required periphirals to control and monitor electric motors, e.g: PWM, Quadrature Encoders and CAN interface.

The TM4C is an ARM Cortex M4 MCU with a maximum frequency of 80MHz.