# Popeye

Basics of containerizing applications and describing multi-containers infrastructures with Docker and Docker Compose.

There are five elements constituting the application:
- Poll, a Flask Python web application that gathers votes and push them into a Redis queue.
- A Redis queue, which holds the votes sent by the Poll application, awaiting for them to be consumed by
the Worker.
- The Worker, a Java application which consumes the votes being in the Redis queue, and stores them into
a PostgreSQL database.
- A PostgreSQL database, which (persistently) stores the votes stored by the Worker.
- Result, a Node.js web application that fetches the votes from the database and displays the result

The app application is given to us, we modify it in order to be compatible with the images and containers we set with our Dockerfiles and the docker-compose.yml

![image](https://user-images.githubusercontent.com/108436798/223157293-f5ce84c7-01ce-4e06-a002-796cab2a6697.png)

<h2>Launch</h2>
Install docker and docker compose in your OS
Steps to follow at root:
<ul>
<li>  docker compose build </li>
<li>  docker compose up </li>
</ul>

![image](https://user-images.githubusercontent.com/108436798/223157985-a7f50edc-bea7-471f-b487-272250383918.png)

Services deployed, CLion view

Once deployed, Poll frontend is at: http://172.19.0.3/

Result frontend is at: http://localhost:5001/
