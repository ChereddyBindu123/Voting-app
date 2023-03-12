# Voting-app
Please find below sample code for voting application:
https://github.com/ChereddyBindu123/sample-voting-app
Building Voting- application using Docker:

--make sure that docker is installed in your linux machine or not, if not install the docker using below command:
# yum install docker*

--once docker is installed, start the docker using below command:
# systemctl start docker

--once it is done clone the voting-project into our local and go to the path where we have project related files and then 
build docker images:
# git clone https://github.com/BretFisher/example-voting-app.git
# ll
# cd vote-app/

#Build vote image
cd vote
#docker build -t vote .

#To check the existing docker images use below command:
#docker images

#Build worker image
#cd ../worker/ 
# docker build -t worker .

#Build result image
#cd ../result/
# docker build -t result .

#To launch redis container use below command:
#docker run -it -d -p 6379 --name redis:alpine3.17
#docker ps --> to check the available containers

#To launch vote container use below command:
#docker run -it -d --name vote --link redis:redis -p 5000:80 vote
#docker ps

#Access the vote container via link: https://Ip address:5000

#To launch postgres db container use below command:
#docker run -it -d --name db -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres -v db-data:/var/lib/postgresql/data postgres
#docker ps

#To launch worker container use below command:
#docker run -it -d --name worker --link redis:redis --link db:db worker
#docker ps

#To launch result container use below command:
#docker run -it -d --name result --link db:db -p 5001:80 result
#docker ps

#Access the result container via link: https://Ip address:5001


