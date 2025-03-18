# Database-Management-with-Aws-RDS

## 2.1. Creating the database

- Navigate to the search bar and enter RDS
  ![image](https://github.com/user-attachments/assets/ec39d2f3-a9db-4827-a544-2031354ed230)

  - Go to the database section
    ![image](https://github.com/user-attachments/assets/de8d1dc4-9a23-4d5f-b530-f28dfc1268ae)

    - Go to Create database and click
      ![image](https://github.com/user-attachments/assets/cd9369f9-0a71-4f43-97e7-bd955436078d)

      - Once you enter the Create databse panel select Standard create
        ![image](https://github.com/user-attachments/assets/5d8074fb-5c9d-4ad4-9420-b302b98e1846)

       - Select the mysql engine type
         ![image](https://github.com/user-attachments/assets/bd928400-82a3-4d87-9c75-d38cf764d7b4)

      - For the engine version we will be selecting the version 8.0.35
         ![image](https://github.com/user-attachments/assets/2f7f471d-3127-4c11-8ab4-971b7ae737a1)
        - For our template we will be using the free version
          ![image](https://github.com/user-attachments/assets/7205b1fc-09f2-4964-995a-3c3b42c6b7a3)

          - Enter the name of your Database
            ![image](https://github.com/user-attachments/assets/a6527729-74f4-40c4-a3c7-9f83987250aa)

            - enter your master password and make sure you store it somewhere accessible for future access
              ![image](https://github.com/user-attachments/assets/ef53c337-d606-4e01-a1d3-80529f021757)

             - Select your already existing VPC , confirm it has more than one availability zone
              ![image](https://github.com/user-attachments/assets/7719034a-6491-4f99-8887-a8e6f4f562e8)

          - Grant it public access
            ![image](https://github.com/user-attachments/assets/df8d6ca8-fe99-4609-9583-63eaa703dd5a)

            - Select an existing Security group and ensure that it permits traffic on port 3306 for al CIDR range
              ![image](https://github.com/user-attachments/assets/4f9afb6a-bd8f-4f3c-aa3f-feddaf8affb1)

              - This is what it should look like
                ![image](https://github.com/user-attachments/assets/ee7313b5-020a-41d0-b5a5-7f9022d36566)

                - Enter your Availabilty zone
                  ![image](https://github.com/user-attachments/assets/6cf18cc2-0e71-4a2b-a3af-1304f3dc89e1)

                - For Database authentication select password
                  ![image](https://github.com/user-attachments/assets/c1534ef0-e991-4b79-baf6-4e91bff536d9)

                  - Then finalize and Create your database
                    ![image](https://github.com/user-attachments/assets/2f82b320-c4ac-4c3f-8c2b-f6ac5aff1239)
               
                - It has been created

                     ![image](https://github.com/user-attachments/assets/34a592c5-d8ff-4dba-b198-9c82d52b0a20)



 






 


    


## 3.1. EC2 Instance for the RDS
  - ssh into your Ec2 instance
    ![image](https://github.com/user-attachments/assets/d45d8173-a995-4a3e-9792-d5cefe7dd49c)

    - Once you get access , download the download package for the mysql server
    - ![image](https://github.com/user-attachments/assets/42ebec0d-4fb1-400d-95ba-69829acd5214)

     - This is the downloaded package
      ![image](https://github.com/user-attachments/assets/1b1d6be0-0612-4e9f-8cbb-eada7180abbe)
- You update the server operating system
   ![image](https://github.com/user-attachments/assets/2a4e937d-7794-4fe1-8c49-42b489849abb)
 - You then run the highlighted command to install the package
   ![image](https://github.com/user-attachments/assets/7bc2afb2-29a9-409e-a5bb-a290eb09e776)

   - It is done installing
    ![image](https://github.com/user-attachments/assets/ff64e5d5-2310-4340-a50e-ef7064e50ed0)

- To check it was installed
  ![image](https://github.com/user-attachments/assets/075045b7-07b4-4aa9-862d-e730c4171bd9)

  - Run the below command so that the service starts automatically
    ![image](https://github.com/user-attachments/assets/6bcfd3bb-c64c-4a89-b4dc-370a63f869cb)

   - In order to connect our EC2 instance to our RDS, enter the highlighted command
    ![image](https://github.com/user-attachments/assets/ef84a61b-ca0f-4b2e-8c9f-b4dacf28e042)

     - It promptes you for your password, you then enter it and mysql is launched
   ![image](https://github.com/user-attachments/assets/23f2f153-8f71-448a-a366-68eff1a6898a)

Now you have access to the database



      

   

  



  

   
        


