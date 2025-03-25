## manual install
 - install nodejs 
 - clone the repo
 - install dependendcies
 - start db locally
    - run 
    - postgres_password=mysecretpassword -d -p 5432
# docker installation
 - Install docker
 - Create a network - docker network create user_project
 - Start postgres
   - docker run --network user_project --name postgres -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres
 - Build the image - docker build --network=host -t user-project .
 - Start the image - docker run -e DATABASE_URL=postgresql://postgres:mysecretpassword@postgres:5432/postgres --network user_project -p 3000:3000 user-project
# docker-compose installation
 - Install docker, docker-compose
 - Run docker-compose up