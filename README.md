# Modul Graph Docker Setup

This repo contains a docker-compose definition for easy deployment of the Modul-Graph application.

## Configuration

For configuration make changes to the .env file (or the docker-compose for more drastic changes).


**The default configuration can be used to create a local playground** 
By default the WebUI can be accessed under: `http://localhost:3000`.

### Variable MODUL_GRAPH_NEXT_PUBLIC_API_URL

Defines under which base url the WebUI can access the backend

### Variable MODUL_GRAPH_NEXT_API_URL

Defines under which URL the Frontend Server can reach the backend. Keep in mind that the Frontend server runs inside a docker container!

If the hostname to that the WebUI can reach is the same that the frontend server can reach you can comment out this variable.

*If MODUL_GRAPH_NEXT_PUBLIC_API_URL has localhost as hostname this must be set.*

In in doubt use: `http://backend:8080/api/v1` as value.


### Variable MODUL_GRAPH_FRONTEND_PORT

Port the frontend will be reachable under on the host network

### Variable MODUL_GRAPH_NEO4J_PASSWORD

Password used by the backend to communicate with neo4j. 

Neo4J will be setup with this password initially. After inital setup Neo4J won't respect changes to this variable!


## Startup

Run `docker compose up` to start the application. 
Recommended: If you want to start off with an existing Modul-Graph run the following: `docker compose exec backend python -m modul_graph --recreate-graph`

## Usage.

The WebUI has 2 parts: 

### Teacher-View

Can be accessed in the existing Modul-Graph under in the WebUI: `/sc/SPO%202017%20Informatik%20(Start%20Wintersemester)/teacher_view`

### Student-View

Can be accessed in the existing Modul-Graph under in the WebUI: `/sc/SPO%202017%20Informatik%20(Start%20Wintersemester)/student_view`
