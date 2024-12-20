# monica-arm32v6
Build [monica](https://github.com/monicahq/monica) on your old [Raspberry Pi 1 Model B+](https://www.raspberrypi.com/products/raspberry-pi-1-model-b-plus/) using the arm32v6 images available (based on the official [docker image description](https://hub.docker.com/_/monica))

### Generate your own APP_KEY by using the following command and replace the example one on the .yml file:
> echo -n 'base64:'; openssl rand -base64 32

### Database and files will be stored in folders:
- data/
- mysql/

### Create your own secrets:
- For mysql regular user: create a **db_user.secret** file and place your password inside
- For mysql root user: create a **db_root.secret** file and place your password inside
- Create a *.env.local* file replacing all you need from the original .env file

### To build and run:
> docker compose up -d

After a few minutes (you could monitor the status by removing -d from the previous command or execute docker logs) you should be able to access to the instance with {raspberry-ip}:8080. You might need to open ports in order to connect to the application/database from another computer. I'd recommend to use ufw to do so.
