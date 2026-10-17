# Skill Test 1 :  Cloud and Containers 

---------------------------------------

Hi Team below  documentation includes Setup instructions , How to test each service , Basic troubleshooting tips and Screenshots showing services running in Docker as expected in test documents. 



I have Assigned Port to each service as below

```
---------------------------------
   i) user-service      - 3000
   ---------------------------
   ii) product-service  - 3001
   ---------------------------
   iv) gateway-service  - 3003
   ---------------------------
   v) Order Service     - 3002
---------------------------------
```

#Setup Instructions :

```
1.    Install Docker Desktop with Docker Compose and Git, and make sure Docker is running.
2.    Fork and Clone the forked repo using VS code .
3.    Go to the project folder: Run cd Microservices-Task/Microservices, where docker-compose.yml lives.
4.   Check the ports are free 3000, 3001, 3002 and 3003
5.   Update docker file for each service
6.   Create docker-compose.yml
7.  Run docker compose config to confirm the compose file is valid.
8.  Build and start everything
9.  Verify containers are running
10.  Test each service with curl and also on browser
11.  Test network output
12.  Stop and clean up: Run docker compose down to stop and remove the containers and network.
```

----------------------------------------------------------------------------------------------

  # Detailed Steps 
1. Confirmed status of docker and git

<img width="1187" height="546" alt="image" src="https://github.com/user-attachments/assets/608f1b9f-9ef4-48e3-bca6-ac8a0c8f9b84" />

2. Fork and Clone the forked repo using VS code .
   i)  Forked repository : https://github.com/mohanDevOps-arch/Microservices-Task.git
<img width="1194" height="679" alt="image" src="https://github.com/user-attachments/assets/191a9c3b-aa46-45b4-95d5-f5bb8e562383" />

ii) Cloned the forked repository:
<img width="1196" height="435" alt="image" src="https://github.com/user-attachments/assets/1c9df989-bdf3-4bf8-be07-a9a74e055846" />

3.  Added Dockerfiles for respective services
   <img width="1192" height="222" alt="image" src="https://github.com/user-attachments/assets/8f63342f-6759-4132-a3d5-18f7c66c110f" />

4. Build and tested one Service
   i) Build
   <img width="1191" height="368" alt="image" src="https://github.com/user-attachments/assets/f23b1b1b-ed4f-4d37-8c35-1ca524ef74cb" />
   ii) Test
<img width="1195" height="102" alt="image" src="https://github.com/user-attachments/assets/80cd8fe0-2967-4f44-b570-1b478c8833d7" />
<img width="1197" height="300" alt="image" src="https://github.com/user-attachments/assets/3f9e03b5-81e2-4335-8646-57494b003cd2" />

5. Added and validated docker-compose.yml file
   <img width="1190" height="75" alt="image" src="https://github.com/user-attachments/assets/772ed845-9a0b-4ebb-ab57-e12a462f721d" />
<img width="1086" height="715" alt="image" src="https://github.com/user-attachments/assets/c1b3fa88-e3fa-4dc4-bc40-301eb4d4f951" />

6.  Build and started  all services:
   
<img width="1079" height="653" alt="image" src="https://github.com/user-attachments/assets/bd1ffd5c-9ba9-4d5a-80a0-7a124db38474" />
<img width="1083" height="421" alt="image" src="https://github.com/user-attachments/assets/572344a0-4300-45e5-8e6c-1bd488568308" />

   
 7. Screenshots showing services running in Docker :

   <img width="1082" height="102" alt="image" src="https://github.com/user-attachments/assets/9a8ecb26-0c40-46de-9d3c-7e70727c60fc" />

8. Docker Compose Logs

    <img width="1088" height="143" alt="image" src="https://github.com/user-attachments/assets/24d596c5-f743-455e-baf1-5b8c6f32db73" />

 
9.Tested  each Service with curl also in browser 
 
```bash
curl http://localhost:3000/users          # User service
curl http://localhost:3001/products       # Product service
curl http://localhost:3003/api/users      # Gateway -> User service
curl http://localhost:3003/api/products   # Gateway -> Product service
```

<img width="1086" height="340" alt="image" src="https://github.com/user-attachments/assets/9011d56e-3723-473f-835e-063cb8ae7584" />



<img width="1084" height="212" alt="image" src="https://github.com/user-attachments/assets/35c07cf8-0d4d-42eb-9fe3-3f9a42b82f7a" />


<img width="1085" height="196" alt="image" src="https://github.com/user-attachments/assets/59610dbc-b85d-4e82-900c-6baa8cd59ba8" />

<img width="1084" height="158" alt="image" src="https://github.com/user-attachments/assets/0a9f9dc7-e14c-49a0-823f-5f620f85ab73" />
<img width="1085" height="197" alt="image" src="https://github.com/user-attachments/assets/aed77d0e-9ed4-4da8-b450-7a1b49726400" />
<img width="1084" height="152" alt="image" src="https://github.com/user-attachments/assets/b18d9c48-17cf-436e-bdf6-9f351b01e4bf" />

<img width="1085" height="124" alt="image" src="https://github.com/user-attachments/assets/1eed4321-6daa-47c1-90ee-1ed031803419" />


10. Network output

    <img width="1082" height="690" alt="image" src="https://github.com/user-attachments/assets/184782c9-30d3-4b1a-8ed1-37971616caa9" />


11. Shutdown Docker compose

    <img width="1238" height="210" alt="image" src="https://github.com/user-attachments/assets/07efed43-3ac1-4b33-989c-be76d3c21cce" />


## Basic Troubleshooting Tips.


```
1.  When we get  Cannot connect to Docker daemon error  check if  Docker Desktop is not running, just open it and retry ---> open -a docker
2.  If you get Port already in use error , check any process running on that port , if its not required kill and re-run build.
3.  I witnessed this error today --> Error: Cannot find module '/usr/src/app/index.js - there was  wrong file name in CMD, corrected it --> CMD ["node", "app.js"]
4.  If any command is giving unexpected results,  check for typos and spaces correct it and rerun.
5.  Make sure port numbers assigned to each service are correct in each Dockerfile.
6.  Create .dockerignore to avoid the issue you may face while pushing code to Git.

