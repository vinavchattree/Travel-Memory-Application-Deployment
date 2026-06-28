# Travel-Memory-Application-Deployment
Deploy Travel Memory App (heroVired)

Create Backend Servers
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

 Create frontend servers

 1) Use same user data code as used for backend and create new EC2 instance

    <img width="1350" height="551" alt="image" src="https://github.com/user-attachments/assets/31699263-873b-4a82-8fd8-08f7e8098e1d" />

 2) Make changes in src/url.js to add backend IP.


    <img width="1319" height="664" alt="image" src="https://github.com/user-attachments/assets/85f8e041-1404-4990-bab6-dcad33537ba6" />


3) Install npm and start

<img width="940" height="397" alt="image" src="https://github.com/user-attachments/assets/807ea10d-3958-4799-8619-b7ae82294472" />

4) Install nginx and forward requests to port 3000

   <img width="1136" height="581" alt="image" src="https://github.com/user-attachments/assets/56b1ef43-77c1-40bb-833d-3923ad20eda8" />
   
5) Check if you can access app from this IP.


<img width="940" height="359" alt="image" src="https://github.com/user-attachments/assets/8ddefa43-edd0-4584-b853-3929842fc83f" />

6) You can test it here.
<img width="940" height="361" alt="image" src="https://github.com/user-attachments/assets/a86718b6-f2d8-493f-931b-fec9834db5a2" />

<img width="940" height="451" alt="image" src="https://github.com/user-attachments/assets/2d8ab235-4411-4cb0-8b04-7e0adccffae7" />




   


Create AMIs
1) Create image from frontend and backend server

   <img width="940" height="396" alt="image" src="https://github.com/user-attachments/assets/2eb9a8a8-8f3f-4053-a5b2-c803eab5ddc1" />

   <img width="1341" height="408" alt="image" src="https://github.com/user-attachments/assets/7ae22381-c63f-4223-a0b6-66e7f5e9142a" />


2) Create Ec2 instances from image. Change availabaility zone (use subnet for another availability zone)

   <img width="1341" height="408" alt="image" src="https://github.com/user-attachments/assets/b488c9f2-c277-4e6d-8e29-af017e168b11" />


   <img width="940" height="369" alt="image" src="https://github.com/user-attachments/assets/49898f9e-4999-456c-9ae6-3b809e8b21ec" />




Load Balancing


1) Create traget groups for both frontend and backend and add servers in those traget groups

   <img width="940" height="382" alt="image" src="https://github.com/user-attachments/assets/39e76eb7-198b-49c5-aef7-c22400a8d596" />

2) Create a load balancer using application load balancer and add the frontend target group. Do the same for backend target group.

   <img width="940" height="380" alt="image" src="https://github.com/user-attachments/assets/b298dec0-49fd-41f1-98cf-e7f4f741804e" />


3) <img width="906" height="391" alt="image" src="https://github.com/user-attachments/assets/91b7b5e8-5144-41d4-9583-6cba05ab621b" />


Add CDN

1) Go to cloudflare and add cname records for domain vinav

   <img width="940" height="344" alt="image" src="https://github.com/user-attachments/assets/d8f6224d-6c6c-4b29-93e1-7efdc399f238" />

2)  Add the DNS servers allotted by Cloudflare to the domain nameservers.

   <img width="1358" height="615" alt="image" src="https://github.com/user-attachments/assets/2a781f1a-c7cd-48ee-9a09-b45d7550b2e8" />


3) Wait for 5 min and try to restart npm and node on frontend servers

  <img width="940" height="505" alt="image" src="https://github.com/user-attachments/assets/3bd4fdad-cb6c-46d7-a76a-297ceb140447" />


  <img width="940" height="488" alt="image" src="https://github.com/user-attachments/assets/ca4299e2-dad4-4129-bb45-216bc5401819" />


   


   


   



   

   




   



   
   



    


    


   



