# Python and PostgreSQL with docker compose

Python REST API app that connects to PostgreSQL that can store and retrieve user data.

### Building and running your application

>Before starting the app, make sure change the **postgres.env.example** file to **postgres.env** and **.env.example** file in app/ dir to **.env**, and change the password values inside.

When you're ready, start your application by running:

`$ docker compose up -d`

Your application will be available at http://localhost:5000.

### Creating User and Retrieving it
``$ curl -X POST http://localhost:5000/user -H "Content-Type: application/json" -d '{"username": "john_doe", "email": "john@example.com"}'``

``$ curl -i http://localhost:5000/user/1``

### Note to Remember


1. For Python app:
    >**dotenv** work storing environment variables in .env file and can be accessed by (os.getenv). Need to load module (`from dotenv import load_dotenv`) and env variables (`load_dotenv()`) for access username, password and db name.

    >Errors can happen a lot. Most of them are due to dependency version.
    
2. For PostgreSQL:
    >postgres.env file store env variables for username and password and db name.
    >Healthcheck can be done ``pg_isready -q``. 


