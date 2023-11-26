# monica-arm32v6
Build monica on your old Raspberry Pi model 1 using the arm32v6 images available (based on the original image description https://hub.docker.com/r/arm32v6/monica)

Requirements:
- Docker
- Raspberry pi model 1

Generate your own APP_KEY by using the following command and replace the example one on the .yml file:
- echo -n 'base64:'; openssl rand -base64 32

Database and files will be stored in:
- data
- mysql

Secrets:
- You must create the passwords for the monica and root user.
- For regular user: create a db_user.secret file and place your password inside
- For root user: create a db_root.secret file and place your password inside
