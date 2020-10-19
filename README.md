# Intermediate JS #3: UdaciRacer Simulator
## Overview
**UdaciRacer Simulator** is the third project of Udacity [Intermediate JavaScript](https://www.udacity.com/course/intermediate-javascript-nanodegree--nd032) nanodegree program. It requires to build a racing game which allows a user to race a simulated racer. This racing game runs as a *Node* application. 

The goal of the project is to use the provided starter project to build the web interface for:
* Creating Races (the selection of tracks and pod racers)
* Displaying the real-time race updates
* A final score/rankings view

## Features
Players get to choose their racer and the track they want to race on. The strategy of the game is for each player to choose a pod racer they expect to win over a certain race track based on the pod’s characteristics (acceleration, handling, and top speed). A pre-built API creates the race selected by the players and returns a stream of information lasting the duration of the race, resulting in a final ranking of racers.

The game has three main views:
1. The form to create a race
2. The race progress view (this includes the live-updating leaderboard and acceleration button)
3. The race results view

## API Used
Below is a list of the API endpoints and the shape of the data they return. 

* [GET] ```api/tracks``` List of all tracks
  * id: number (1)
  * name: string ("Executioner")
  * segments: number[] ([87,47,29,31,78,25,80,76,60,14....])
  
* [GET] ```api/cars``` List of all cars
  * id: number (3)
  * driver_name: string ("Anakin Skywalker")
  * top_speed: number (500)
  * acceleration: number (10)
  * handling: number (10)
  
* [GET] ```api/races/${id}``` Information about a single race
  * status: RaceStatus ("unstarted" | "in-progress" | "finished")
  * positions object[] ([{ car: object, final_position: number (omitted if empty), speed: number, segment: number}])
  
* [POST] ``api/races`` Create a race
  * id: number
  * track: string
  * player_id: number
  * cars: Cars[] (array of cars in the race)
  * results: Cars[] (array of cars in the position they finished, available if the race is finished)
  
* [POST] ```api/races/${id}/start``` Begin a race
  * Returns nothing
  
* [POST] ```api/races/${id}/accelerate``` Accelerate a car
  * Returns nothing
  
## Getting Started
To run the project locally,
1. Clone this repo.
2. ```cd``` into project directory.

### Starting Server
To run the server, locate your operating system and run the associated command in your terminal at the root of the project.

| Your OS  | Command to start the API | 
| :--------- | :-------------------------- |
| Mac |  ORIGIN_ALLOWED=http://localhost:3000 ./bin/server-osx | 
| Windows | ORIGIN_ALLOWED=http://localhost:3000 ./bin/server.exe |
| Linux (Ubuntu, etc..)|  ORIGIN_ALLOWED=http://localhost:3000 ./bin/server-linux | 

If you are on an older OS and the above command doesn't run for you - or if you know that you are running a 32bit system - add -32 to the end of the file name. For reference, here are the same commands but for a 32-bit system.

| 32 Bit Systems Only! | Command to start the API | 
| :--------- | :-------------------------- |
| Mac |  ORIGIN_ALLOWED=http://localhost:3000 ./bin/server-osx-32 | 
| Windows | ORIGIN_ALLOWED=http://localhost:3000 ./bin/server-32.exe |
| Linux (Ubuntu, etc..)| ORIGIN_ALLOWED=http://localhost:3000 ./bin/server-linux-32 | 

**NOTE:** this process will use your terminal tab, so you will have to open a new tab and navigate back to the project root to start the front end.

### Starting Frontend
To start the frontend, run one of the following commands from the root folder.
```
npm install && npm start
```
```
yarn && yarn start
```
  
## Authors
Alexandra Baturina
