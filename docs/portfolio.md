---
layout: page
title: Portfolio
permalink: /portfolio
published: true
---

## Table of Contents
- [Capstone Project](#capstone-project)<br>
- [BEAVS Simulation](#beavs-simulation)<br>
- [ESRA Final Technical Report]()
- [OPEnS Lab FloDar Project Lead](#opens-lab-flodar-project-lead)<br>
- [FIRST Robotics Team Experience](#first-robotics-team-experience)<br>
- [RingGame](#ringgame)<br>

<br>

<!-- PROJECTS BEGIN HERE -->

<hr>
### Capstone Project
*2023 - 2024*

...

<hr>
### [BEAVS Simulation](https://github.com/DexterCarpenter/BEAVS4-Simulation)
*2024*

This project involed writing a simulation for Oregon State University's Experimental Sounding Rocket Association Team. The simulation is used to gain understanding of how the **Blade Extending Apogee Variance System (BEAVS)** will affect the rocket's flight path. The simulation takes [OpenRocket](https://openrocket.info/) data export in conjunction with [OpenMotor](https://github.com/reilleya/openMotor) custom motors as a basis.

Objectives
- Understand the total braking power of BEAVS given varying rocket designs
- Separation failure risk analysis
- PID control simulation
- Output data to BEAVS hardware to simulate flight (did not achieve)

The first objective was to understand the total braking power of BEAVS given varying rocket designs. Early in the development process the propulsion team needed to determine how large to make the rocket motor. To determine this, the team needed to understand how much BEAVS could theoretically reduce the apogee by. This was a very large first leap. To achieve this, the aerodynamic drag problem must be solved, a process for importing simulated rocket flight data into MATLAB must be written, and a solution to calculate how BEAVS’s change to the drag will affect the flight. All these problems are solved with the Control Range Graphic shown below.

<p align="center"><img src="/assets/ControlRangeGraphic.png" alt="ControlRangeGraphic" class="center"/></p>

This graphic highlights the minimum and maximum BEAVS could lower the apogee by. The solid blue line represents the rocket’s altitude over time if no air braking occurs. This is equivalent to the direct data import from OpenRocket. The dashed blue line represents a maximum braking scenario and can be interpreted as the most that BEAVS could brake, if needed. The orange lines show the total coefficient of drag of the entire rocket over time.

Due to the location of BEAVS being on the lower (aft) section of the rocket, there is a high risk of separation failure. Separation failure occurs when the lower section has more drag than the forward section such that it causes the two sections to separate before it reaches apogee. This would be catastrophic for the competition. To mediate this failure mode, the MATLAB simulation calculates the force exerted by BEAVS and the force felt at the coupler between the two sections. This is represented in the following figure.

<p align="center"><img src="/assets/ForcesDuringCoast.png" alt="ForcesDuringCoast" class="center"/></p>

Due to the difficulty of testing BEAVS, it was required that the MATLAB simulation also implements the [PID control system](https://en.wikipedia.org/wiki/Proportional%E2%80%93integral%E2%80%93derivative_controller). The simulation was written initially with this functionality in mind. The simulation takes an input for the blade extension and calculates the force of drag it will induce. The system is iteratively solved using [Forward Euler](https://en.wikipedia.org/wiki/Euler_method). At each time step, the PID function compares the current velocity to a target velocity using a height to velocity lookup table. Then outputs a desired blade extension amount. This desired blade extension amount is then fed to another function that evaluates whether the blades can be adjusted to the desired position. If possible, give a constant blade extension/retraction rate, the blade extension is set to the desired position. If the desired position is unreachable in the time step, it extends the most it could in the time step and returns that position to the Forward Euler iterator. Using this, K<sub>p</sub>, K<sub>i</sub>, and K<sub>d</sub> values can be found with manual tuning. The following figure shows the error in velocities over time given a sample initial data set.

<p align="center"><img src="/assets/PIDGraphic.png" alt="PIDGraphic" class="center"/></p>

<hr>
### [ESRA Final Technical Report](https://www.dropbox.com/scl/fo/1esn53zry4i2fjv8t0i5m/ABTbk8A2A9bhiVj74qt7v-0?dl=0&e=1&preview=Team_68_Technical_Report_2024_Spaceport_America_Cup.pdf&rlkey=chkbse71359m5jrlwx5wczgy6&st=6go4n431)
*2024*

...

<hr>
### [OPEnS Lab FloDar Project Lead](https://github.com/OPEnSLab-OSU/FloDar)
*Jan 2021 - Oct 2022*

...

<hr>
### FIRST Robotics Team Experience
*2016 - 2019*
# Freshman Year: Joining the Team
I joined our [FIRST robotics team](https://www.pigmice.com/) as a freshman, eager to immerse myself in the world of engineering and robotics. This initial year provided a foundation in teamwork, basic mechanical concepts, and the excitement of competitive robotics.

# Sophomore Year: Build Lead
In my sophomore year, I was appointed as the Build Lead. Under the mentorship of the Manufacturing Captain, I gained invaluable experience in leadership and hands-on engineering. Our department was responsible for transforming designs from the Design Department into functional components for our robot. We began prototyping with wood and cardboard, allowing for quick iterations and testing. Once designs were finalized, we manufactured the parts using aluminum, ensuring durability and precision.

# Junior Year: Co-Leading as Manufacturing Captain
My junior year marked a significant step forward as I was elected to co-lead as the Manufacturing Captain. This role intensified my responsibilities and honed my skills in organization, communication, and managing a team under stressful environments. Our hard work and improved processes paid off, as we advanced to the District Championships for the first time in many years. This achievement was a testament to our improved design, iteration, and testing methods.

![Otis](/assets/Otis.jpg "Otis")

# Senior Year: Team Captain
In my senior year, I was honored to be elected as the Team Captain, co-leading the entire team. My focus on leadership, organization, and fostering effective communication among team members culminated in an exceptional season. We advanced to the World-level competition in Houston, TX, where we became finalists in the playoffs of our division. Our team’s journey ended only after a closely contested match with the eventual world champions.

![Celebrating](/assets/PigmiceHouston.JPG "Celebrating getting to finals")

Throughout my journey with the FIRST robotics team, I developed a strong foundation in engineering principles, leadership, and teamwork. These experiences have significantly shaped my approach to problem-solving and project management, skills that I continue to apply in my ongoing engineering endeavors.

![Scorpion](/assets/scorpion.webp "Scorpion")

<hr>
### [RingGame](https://github.com/DexterCarpenter/RingGame)
*2020*

An Arduino-based arcade style game. Press the button when the lights line up to proceed to a faster level. 

This was a one-day project. Using a Adafruit Neopixel ring (24), an Arduinio Uno, and a button I created a game where the objective is to press the button when the "runner" and the "selector" are aligned. If you are successful, you get a green flash and the runner gets faster. This proceeds until you miss, in which an animation plays and restarts the runner's speed.

My goal was to make this as simple as possible, using just the NeoPixel and a button as the UI.

![RingGame](/assets/RingGame.gif "RingGame")