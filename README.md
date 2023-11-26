# monica-arm32v6
Build monica on your old Raspberry Pi model 1 using the arm32v6 images available (based on the original image description https://hub.docker.com/r/arm32v6/monica)

Requirements:
- Docker
- Raspberry pi model 1

Generate your own APP_KEY by using the following command and replace the example one on the .yml file:
- echo -n 'base64:'; openssl rand -base64 32

Database and files will be stored in folders:
- data/
- mysql/

For secrets you must create your own (one for monica and another one for the root user):
- For regular user: create a **db_user.secret** file and place your password inside
- For root user: create a **db_root.secret** file and place your password inside

To build and run:
- docker compose up -d

After a few minutes (you could monitor the status by removing -d from the previous command or execute docker logs) you should be able to access to the instance with {raspberry-ip}:8080. You might need to open ports in order to connect to the application/database from another computer. I'd recommend to use ufw to do so.

To finalize, the official documentation asks you to do:
- docker exec -it monica-app-1 php artisan setup:production
