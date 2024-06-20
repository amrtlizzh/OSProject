# OSProject Running Containers for Application Development

Group Name: __Linux Runner__. 

Section: __Section 2__. 

Team Mates:
1. __RABIATUL ADAWIYAH BINTI MOHD ALWI__ and __2217808__
2. __SHARIFAH SYAZWINA BINTI SYED SYAMSULHARIS__ and __2214326__
3. __NUR AMIROTUL IZZAH BINTI MOHAMAD FAIZAL__ and __2216966__


***Questions:***

1. What is the link of the fork OSProject in your repository. ***(1 mark)***
<br> __https://github.com/amrtlizzh/OSProject__.
2. How many files and folders are in this repository. ***(1 mark)*** __<br>  __- 1 readme.md file__
 <br>  __- 1 images folder____.


## Exploring github codespaces

***Questions:***

1. What is default OS used to run the virtual environment for codespaces. ***(1 mark)***<br> __Ubuntu Linux__.
2. What are the two options of ram, disk and vcpu configuration you can have in running codespaces . ***(1 mark)*** 
<br> <img src="./images/configuration.png" width="70%"> <br> __1. VCPU 2-CORE: RAM = 8GB DISK = 32GB <br> 2. VCPU 4-CORE: RAM = 16GB DISK = 32GB__.
3. Why must we commit and sync our current work on source control? ***(1 mark)*** <br>__To saves changes to local repository, pulls changes from the remote to sync with local changes, and then pushes changes to the remote repository.__.

## Exploring the Terminal

***Questions:***

Look at the TERMINAL tab. Run the following commands and provide the output here. 

1. Run the command **pwd** . ***(1 mark)*** <br> <img src="./images/command1.jpeg" width="70%">
2. Run the command **cat /etc/passwd** . ***(1 mark)*** <br> <img src="./images/command2.jpeg" width="70%">
3. Run the command **df** . ***(1 mark)*** <br> <img src="./images/command3.jpeg" width="50%"> 
4. Run the command **du** . ***(1 mark)***
<br> <img src="./images/command4p1.jpeg" width="20%">
<br> <img src="./images/command4p2.jpeg" width="20%">.
<br> <img src="./images/command4p3.jpeg" width="20%">.
<br> <img src="./images/command4p4.jpeg" width="20%">.
5. Run the command **ls** . ***(1 mark)***
<br> <img src="./images/command5.jpeg" width="70%">.
6. Run the command **ls -asl** . ***(1 mark)***
<br> <img src="./images/command6.jpeg" width="70%">.
7. Run the command **free -h** . ***(1 mark)***
<br> <img src="./images/command7.jpeg" width="70%">.
8. Run the command **cat /proc/cpuinfo** . ***(1 mark)*** 
<br> <img src="./images/command8a.jpg" width="20%">.
<br> <img src="./images/command8b.jpg" width="70%">.
<br> <img src="./images/command8c.jpg" width="20%">.
<br> <img src="./images/command8d.jpg" width="70%">
9. Run the command **top** and type **q** to quit. ***(1 mark)*** <br> <img src="./images/command9.jpeg" width="70%">.
10. Run the command **uname -a**. ***(1 mark)*** <br> <img src="./images/command10.jpeg" width="70%">.
11. What is the available free memory in the system. ***(1 mark)*** <br> __```512 Mi```__.
12. What is the available disk space mounted on /workspace. ***(1 mark)*** __```20772316 Mi```__.
13. Name the version and hardware architecture of the linux Virtual environment. ***(1 mark)*** <br> __```Linux codespaces-63a3c6 6.5.0-1021-azure #22~22.04.1-Ubuntu SMP Tue Apr 30 16:08:18 UTC 2024 x86_64 x86_64 x86_64 GNU/Linux```__.
14. What is the difference between **ls** vs **ls -asl**. ***(1 mark)*** <br> __```The ls command lists files and directories in the current directory. The ls -asl command lists all files and directories in the current directory with detailed information, including hidden files, sizes, permissions, and ownership.```__.
15. What is the TLB size of the Virtual CPU. ***(1 mark)*** <br>
__```2560 4K pages.```__.
16. What is the CPU speed of the Virtual CPU. ***(1 mark)*** <br> __```3026.803 ```__.
17. What is the top running process that consumes the most CPU cycles. ***(1 mark)***  <br> __```top - 07:31:45 up  3:26,  0 users,  load average: 0.08, 0.15, 0.16 ```__.

## Running your own container

***Questions:***

1. Are files in the container persistent. Why not?. ***(1 mark)*** <br> __Files in a container are not persistent because containers are designed to be temporary and easily disposaable. When a container is deleted, its filesystem and any files inside it are also deleted.__.
2. Can we run two, or three instances of debian linux? . ***(1 mark)*** <br> __Yes, because each container acts like a separate debian linux system, allowing running multiple instances at once.__.

## Running your own container with persistent storage

***Questions:***

1. Check the permission of the files created in myroot, what user and group is the files created in docker container on the host virtual machine? . ***(2 mark)*** __Fill answer here__.
2. Can you change the permission of the files to user codespace.  You will need this to be able to commit and get points for this question. ***(2 mark)***
```bash
//use sudo and chown
sudo chown -R codespace:codespace myroot

```
*** __Fill answer here__.***

## You are on your own, create your own static webpage

***Questions:***

1. What is the permission of folder /usr/local/apache/htdocs and what user and group owns the folder? . ***(2 mark)*** __Fill answer here__.
2. What port is the apache web server running. ***(1 mark)*** <br> __```8080```__.
3. What port is open for http protocol on the host machine? ***(1 mark)*** <br> __```8080```__ <br> <img src="./images/webpage.jpg" width="70%">.

## Create SUB Networks

1. In docker, you can create your own private networks where you can run multiple services, in this part, we will create two networks, one called bluenet and the other is rednet
2. Run the docker create network to create you networks like the ones below
```bash
## STEP 1:
## Create Networks ##
docker network create bluenet
docker network create rednet`

## STEP 2: (automatically running)
## Create (1) Container in background called "c1" running busybox image ##
docker run -itd --net bluenet --name c1 busybox sh
docker run -itd --net rednet --name c2 busybox sh
```
***Questions:***

1. Describe what is busybox and what is command switch **--name** is for? . ***(2 mark)*** __Fill answer here__.
2. Explore the network using the command ```docker network ls```, show the output of your terminal. ***(1 mark)*** __Fill answer here__.
3. Using ```docker inspect c1``` and ```docker inspect c2``` inscpect the two network. What is the gateway of bluenet and rednet.? ***(1 mark)*** __Fill answer here__.
4. What is the network address for the running container c1 and c2? ***(1 mark)*** __Fill answer here__.
5. Using the command ```docker exec c1 ping c2```, which basically tries to do a ping from container c1 to c2. Are you able to ping? Show your output . ***(1 mark)*** __Fill answer here__.

## Bridging two SUB Networks
1. Let's try this again by creating a network to bridge the two containers in the two subnetworks
```
docker network create bridgenet
docker network connect bridgenet c1
docker network connect bridgenet c2
docker exec c1 ping c2
```
***Questions:***

1. Are you able to ping? Show your output . ***(1 mark)*** __Fill answer here__.
2. What is different from the previous ping in the section above? ***(1 mark)*** __Fill answer here__.

## Intermediate Level (10 marks bonus)

### Node.js and MySQL in Docker Containers

This guide will help you set up a simple Node.js website that retrieves a random row from a MySQL database. Both the MySQL server and the Node.js server will run in separate Docker containers on two separate networks. Your job is to make it work by making the two containers in two separate network bridged together.

#### Step 1: Set Up the Docker Network

Create a Docker network to for the two containers.
For mysql, call it **mysqlnet** for nodejs call it **nodejsnet** .

#### Step 2: Set Up the MySQL Container

Run a MySQL container on the created network.

```sh
docker run --name mysql-container --network mysqlnet -e MYSQL_ROOT_PASSWORD=rootpassword -e MYSQL_DATABASE=mydatabase -e MYSQL_USER=myuser -e MYSQL_PASSWORD=mypassword -d mysql:latest
```

#### Step 3: Set Up the Node.js Container

1. **Create a directory for your Node.js application and initialize it.**

    ```sh
    mkdir nodejs-app
    cd nodejs-app
    npm init -y
    npm install express mysql
    ```

2. **Create a file named `index.js` with the following content:**

    ```js
    const express = require('express');
    const mysql = require('mysql');

    const app = express();
    const port = 3000;

    // Create a MySQL connection
    const connection = mysql.createConnection({
      host: 'mysql-container',
      user: 'myuser',
      password: 'mypassword',
      database: 'mydatabase'
    });

    // Connect to MySQL
    connection.connect((err) => {
      if (err) {
        console.error('Error connecting to MySQL:', err);
        return;
      }
      console.log('Connected to MySQL');
    });

    // Define a route to get a random row
    app.get('/random', (req, res) => {
      const query = 'SELECT * FROM mytable ORDER BY RAND() LIMIT 1';
      connection.query(query, (err, results) => {
        if (err) {
          console.error('Error executing query:', err);
          res.status(500).send('Server Error');
          return;
        }
        res.json(results[0]);
      });
    });

    // Start the server
    app.listen(port, () => {
      console.log(`Server running at http://localhost:${port}`);
    });
    ```

3. **Create a Dockerfile for the Node.js application:**

    ```Dockerfile
    # Use the official Node.js image
    FROM node:14

    # Create and change to the app directory
    WORKDIR /usr/src/app

    # Copy application dependency manifests to the container image
    COPY package*.json ./

    # Install production dependencies
    RUN npm install

    # Copy local code to the container image
    COPY . .

    # Run the web service on container startup
    CMD [ "node", "index.js" ]
    ```

#### Step 4: Build and Run the Node.js Container

1. **Build the Docker image for the Node.js application.**

    ```sh
    docker build -t nodejs-app .
    ```

2. **Run the Node.js container on the same network as the MySQL container.**

    ```sh
    docker run --name nodejs-container --network nodejsnet -p 3000:3000 -d nodejs-app
    ```

#### Step 5: Test the Setup

You can now test the setup by accessing the Node.js application in your browser or using a tool like `curl`:

```sh
curl http://localhost:3000/random
```

#### Step 6: Ensure `mytable` is Populated

Make sure you have created the `mytable` table and populated it with some data in your MySQL database for the above steps to work correctly.

You can use the following SQL commands to create and populate the table (run these commands in the MySQL container):

```sql
CREATE TABLE mytable (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  value VARCHAR(255) NOT NULL
);

INSERT INTO mytable (name, value) VALUES ('example1', 'value1'), ('example2', 'value2'), ('example3', 'value3');
```

### Summary

You have now set up a Node.js application in a Docker container on nodejsnet netowrk and a MySQL database in another Docker container on mysqlnet network. Now bridge the two network together.

***Questions:***

1. What is the output of step 5 above, explain the error? ***(1 mark)*** __Fill answer here__.
2. Show the instruction needed to make this work. ***(1 mark)*** __Fill answer here__.



## What to submit

1. Make sure to commit all changes on your source control, and make sure your source control is sync to the repository. 
2. Check your repository link, to see if all the files and answers are included in the repository. 
3. Submit through italeem, by providing the link to your repository.
4. Due by ***AS STATED IN ITALEEM SYSTEM***
