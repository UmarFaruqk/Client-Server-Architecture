## CLIENT-SERVER AIRCHUTECTURE WITH MySQL
Client-Server refers to an architecture in which two or more computers are connected together over a network to send and receive requests between one another.
In their communication, each machine has its own role: the machine sending requests is usually referred as "Client" and the machine responding (serving) is called "Server".
Assuming that you go on your browser, and typed in there *steghub.com*. It means that your browser is considered the "Client". Essentially, it is sending request to the remote server, and in turn, would be expecting some kind of response from the remote server.
Lets take a very quick example and see Client-Server communicatation in action:
1. Open your Ubuntu or Windows terminal and run this command *curl -Iv steghub.com* you should see this ![reference image](/Pictures/pic1.PNG) and if your Ubuntu does not have *curl* you can install it by running *sudo apt install curl*
2. From the picture above the remote server is below output and that the requests from the URL are being served by a computer with an IP address 160.153.133.153 on port 80. 

# The Task Here is To Implement a Client Server Architecture using MySQL Database Management System (DBMS).
To demonstrate a basic client-server MySQL RDBMS, follow the below instructions: 
1. Create and configure two Linux-based virtual servers (EC2 instances in AWS). 
2. server A name - *mysql server*
3. server B name - *mysql client*
4. Install MySQL Server on Both servers that's after you've successfully connected them to your Terminal ![reference image](/Pictures/pic2.PNG)
5. By default, both of your EC2 virtual servers are located in the same local virtual network, so they can communicate to each other using local IP addresses. Use *mysql server's* local IP address to connect from *mysql client*.
6. Open the inbound rule on *mysql server* and add TCP port 3306 and for extra security do not allow all IP addresses to reach your 'mysql server' - allow access only to the specific local IP address of your 'mysql client'. ![reference image](/Pictures/pic3.PNG)
7. Configure MySQL server to allow connection from remote hosts using this command *sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf* replace *bind.address* with *0.0.0.0*
8. From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH. You must use the mysql utility to perform this action.
9. To do that we first of all create a new user database and grant all access to it ![reference image](/Pictures/pic6.PNG) then exit the mysql console 
10. Now log in back into mysql console but this time using the user database you created with the password and if everything is okay you should see this ![reference image](/Pictures/pic7.PNG) 
11. Then next step is to access your just created user database in your *mysql server* shell using your *mysql client* public IP and you should see this ![reference image](/Pictures/pic8.PNG)
12. I also went ahead to access *mysql client* database using mysql workbench and thsi was the result of what I got ![reference image](/Pictures/pic9.PNG) 
13. I finally accessed mysql user just like I did in the terminal ![reference image](/Pictures/pic10.PNG) 

## I HOPE YOU UNDERSTAND THE STEP BY STEP PROCESS WE USED IN CARRYING OUT THIS TASK