# Intermediate JS #3: UdaciRacer Simulator
## Overview
**UdaciRacer Simulator** is the third project of Udacity [Intermediate JavaScript](https://www.udacity.com/course/intermediate-javascript-nanodegree--nd032) nanodegree program. It requires to build a racing game which allows a user to race a simulated racer. This racing game runs as a *Node* application. 

The goal of the project is to use the provided starter project to build the web interface for:
* Creating Races (the selection of tracks and pod racers)
* Displaying the real-time race updates
* A final score/rankings view

## Features
Players get to choose their racer and the track they want to race on. The strategy of the game is for each player to choose a pod racer they expect to win over a certain race track based on the pod’s characteristics (acceleration, handling, and top speed). A pre-built API creates the race selected by the players and returns a stream of information lasting the duration of the race, resulting in a final ranking of racers.

## API Used
API Calls
Below are a list of the API endpoints and the shape of the data they return. 

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
