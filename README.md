<h1 align="center">DoCRL</h1>
<h3 align="center">Double Critic Deep Reinforcement Learning for Mapless Navigation of a Hybrid Aerial Underwater Vehicle with Medium Transition</h3>

<p align="center">
  <img src="https://img.shields.io/badge/PyTorch-v1.9.0-blue"/>
  <img src="https://img.shields.io/badge/Pandas-v1.3.2-blue"/>
  <img src="https://img.shields.io/badge/Numpy-v1.21.1-blue"/>
</p>
<br/>

## Summary
<p align="justify">
  <img src="media/sensor.gif" alt="Hydrone" align="right" width="400">
  <a>Deep Reinforcement Learning (Deep-RL) techniques for motion control have been continuously used to deal with decision-making problems for a wide variety of robots. Previous works showed that Deep-RL can be applied to perform mapless navigation, including the medium transition of Hybrid Unmanned Aerial Underwater Vehicles (HUAUVs). These are robots that can operate in both air and water media, with a future potential for rescue tasks in robotics. This paper presents new approaches based on the state-of-the-art Double Critic Actor-Critic algorithms to address the navigation and medium transition problems for a HUAUV. We show that double-critic Deep-RL with Recurrent Neural Networks using range data and relative localization solely improves the navigation performance of HUAUVs. Our DoCRL approaches achieved better navigation and transitioning capability and a solid generalization of learning through distinct scenarios, outperforming previous approaches.</a>  
</p>

## Setup
<p align="justify">
 <a>Before cloning this repository we need to configure your workspace. To do this proceed with the following commands in your terminal:</a>
</p>

```shell
mkdir -p ~/docrl/src
```
```shell
cd ~/docrl/
```
```shell
catkin_make
```

<p align="justify">
 <a>Now that the workspace is already configured just enter the src folder and clone the repository, finally compile the project. To do this proceed with the following commands in your terminal:</a>
</p>

```shell
cd ~/docrl/src/
```

```shell
git clone https://github.com/ricardoGrando/DoCRL --recursive
```

```shell
cd ~/hydrone/
```

<p align="justify">
 <a>Make sure that our version pf the sonar simulation package is in your workspace::</a>
</p>

```shell
https://github.com/ricardoGrando/gpu_sonar_simulation.git
```

```shell
catkin_make
```

<p align="justify">
 <a>We now need to configure your terminal to accept the commands directed to our Hydrone workspace. For this you can simply copy the line of code below to your .bashrc (or .zshrc if you use zsh instead of bash) or put the code directly into your terminal. Note that if you choose the second option, every time you open a new terminal you will have to give the following command again.</a>
</p>

<p align="justify">
 <a>For <b>bash</b>:</a>
</p>

```shell
source ~/hydrone/devel/setup.bash
```

<p align="justify">
 <a>For <b>zsh</b>:</a>
</p>

```shell
source ~/hydrone/devel/setup.zsh
```

<p align="justify">
 <a>Okay, now your Hydrone is ready to run!</a><br/>
 <a>To train, here is as example:</a>
</p>

```shell
roslaunch hydrone_aerial_underwater_deep_rl deep_RL_hybrid.launch ep:=0 file_dir:=td3_stage_1_tanh_lstm deep_rl:=td3_hybrid3D_tanh_lstm.py world:=stage_1 root_dir:=/home/ricardo/ graphic_int:=true
```

<p align="justify">
 <a>Example to peform the testing:</a><br/>
</p>

```shell
roslaunch hydrone_aerial_underwater_deep_rl deep_RL_hybrid.launch ep:=0 file_dir:=td3_stage_1_tanh_lstm deep_rl:=td3_hybrid3D_tanh_lstm.py world:=stage_1 root_dir:=/home/ricardo/ graphic_int:=true testing:=true x:=2.0 y:=3.0 z:=-1.0 arr_distance:=0.5 m_steps:=5000000 testing_eps:=102
```

## Structure
<p align="justify">
  <a>The way Hydrone works may seem a bit complex and in fact some parts are. We recommend to you visualize yourself how the Hydrone's nodes works
  (with the Hydrone already running) by using the following command:</a>
</p>

```shell
rosrun rqt_graph rqt_graph
```

## Media

<p align="center">
  <img src="media/air_to_water.gif" alt="Hydrone Gif" width="400"/>
  <img src="media/water_to_air.gif" alt="Hydrone Gif" width="400"/>
</p>  

<p align="justify">
  <a>We have the official simulation video posted on youtube, to access it just click on the following hyperlink:</a><a href="https://youtu.be/CiFmqoNj6_4"> Video</a>
</p>

<p align="center">
  <a><i>If you liked this repository, please don't forget to starred it!</i></a>
  <img src="https://img.shields.io/github/stars/ricardoGrando/hydrone_deep_rl_ral?style=social"/>
</p>
