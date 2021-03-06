# TripMeMore server

Server exposing the API for the tripmemore applications

Uses nodeJS with expressJS and mongoDB

Based on a lot of information found on http://scotch.io/tutorials/javascript/build-a-restful-api-using-node-and-express-4

## Installation

Simply run

    npm install
    bower install
    gulp

The package.json file contains everything you need

## Configuration 

Don't forget to setup your details in config/

## Usage

Run the server with

    node server.js

Then point your browser at http://localhost:8080

## Views

Some basic views are visible from /, doing authentication using local signup, twitter and facebook oauth. 

## API

The available routes for the are


### GET /api/pins/ 

Return the list of pins. Two filters are available :

GET /api/pins/?user_id=plop&keyword=truc returns the list filtered by user_id, where any of the place contains 'truc'

### POST /api/pins/

Save a pin. Use postman for your tests !

### GET /api/pins/:pin_id

Fetches and return a pin by id

## Pin schema

Data are stored like this inside mongoDb :

var PinSchema   = new Schema({
   origin: String,
   date : { type : Date, default : Date.now },
   place: Schema.Types.Mixed,
   media: Schema.Types.Mixed
});

with media being something like this : { type: String, content: String }
and place being the result of a query from google place autocomple, as seen in the demo/search.html file link to the project


