# Travel-Memory-Application-Deployment
Deploy Travel Memory App (heroVired)

Create Frontend Servers
1) Create security group with HTTP port, SSH & custom TCP port 3000

   <img width="1604" height="508" alt="image" src="https://github.com/user-attachments/assets/984b41bc-cf92-49ee-90ce-9ca8157ba327" />


2) Create new EC2 with created security group and enabled public IP
<img width="940" height="470" alt="image" src="https://github.com/user-attachments/assets/08029440-8ca4-4e4c-9349-1ae07ac1f1b9" />

3) Add script in user data section while creating EC2 to get code from repository

<img width="940" height="479" alt="image" src="https://github.com/user-attachments/assets/26d16d44-2c0c-4b1e-8f82-f0643589e4f1" />

4) backend server created
  <img width="1358" height="526" alt="image" src="https://github.com/user-attachments/assets/e1118fb6-7309-424d-b20d-4f84938adc43" />

5) <img width="1363" height="518" alt="image" src="https://github.com/user-attachments/assets/99ad89f9-d698-4dde-adea-f16850d78bd8" />


6) Check if nested folders in TravelMemory are properly created.

   <img width="940" height="185" alt="image" src="https://github.com/user-attachments/assets/171da759-cc22-4b41-8acb-c6bae9e5265b" />


 7) Create .env file and add mongodb uri

      <img width="1083" height="263" alt="image" src="https://github.com/user-attachments/assets/774a22db-b8f5-4e46-91c8-ab246153256d" />
      


8) Whitelist IP in mongoDB.

    <img width="1326" height="513" alt="image" src="https://github.com/user-attachments/assets/95d75698-4366-454f-a735-5e0173f1b1c7" />

9)  Install npm and run node js  
    <img width="940" height="346" alt="image" src="https://github.com/user-attachments/assets/1483ca7c-7199-4217-9839-65c8dc85b07b" />
     <img width="940" height="394" alt="image" src="https://github.com/user-attachments/assets/c28635a2-059d-455e-a1be-c9e452053e94" />


10) Install nginx

    <img width="940" height="419" alt="image" src="https://github.com/user-attachments/assets/fd334af5-8d3f-4dff-819d-b7d69169c317" />
   
11) Configure nginx and set proxy pass to forward requests to port 3000 (node js)
     <img width="1046" height="541" alt="image" src="https://github.com/user-attachments/assets/65d9a897-815c-4889-b922-12998a844e2c" />

     <img width="940" height="435" alt="image" src="https://github.com/user-attachments/assets/ce70d707-fcfa-4ff5-9921-796cf118d331" />

12) 









Create backend servers


Create server from images


Create Target Groups


Create Load balancer
