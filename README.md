# nine-men-morris
Nine Men Morris game built for FIT3077

<h1>Access Via Browser</h1>
http://170.64.181.91/
<br>

# About Application
The Application is built in Two parts. <br>
The Client Frontend in React Vite TS <br>
The Server Backend in Java 17 Springboot <br>
<br>
The Restful API the Client interacts with can be found in `server/src/main/java/com/team8/backend/WebController.java`
<br>
The main Project files for Nine Man Morris can be found in `server/src/main/java/com/team8/backend/ninemanmorris`
<br>
The Project has also been dockerized into 2 seperate docker images, and is currently hosted at (Digital Ocean)
and <b>accessible at http://170.64.181.91/</b>
<br>


# Start Backend
`navigate to root`<br>
`cd server` <br>
`./gradlew build` <br>
`java -jar build/libs/backend-0.0.1-SNAPSHOT.jar` <br>

# Start Frontend
`navigate to root`<br>
`cd client` <br>
`npm install` <br>
`npm run dev` <br>

# Instructions & Important to note
1) Advised to start the Backend before the Frontend, as the population of the FE relies on the BE data <br>
2) To move, click, hold, drag and drop the pieces on the board display <br>
3) White player goes first <br>
4) The Backend is hosted on port 9999, and enables cors from all sources, FE is on 5173 <br>
5) Advised to run FE & BE on seperate shell instances

<h1>If you want to use docker images instead</h1>

# Docker (After Building Individual Docker folders)
<p>You may still need to build the gradle</p> <br>
`docker compose build`
`docker compose up`

# Docker (Manual)
`cd server` <br>
`docker build -t 9mm-backend:0.0.1 .` <br> 
`docker run -it  -p9999:9999 backend-image-id` <br>

`cd client` <br>
`docker build -t 9mm-frontend:0.0.1 .` <br>
`docker run -it  -p5173:5173 frontend-image-id` <br>

## Important Note ##
1) In the event that all pieces of a player are in a mill, any of their pieces can be removed.
<br>
2) Placing and removing require a click at the location, and moving pieces require dragging and dropping.
<br>
3) You can revisit games by navigating to the respective game id in the url http://170.64.181.91/game/:id, their states are saved. Or via the same path localy hosted. 
<br>
4) Chat functionality has not been implemented yet, multiplayer has not been optimized yet.
<br>
5) endpoints for project are set to localhost currently but can be set to point to the digital ocean hosted backend at fetchLocation in Menu.tsx, Board.tsx
<br>
