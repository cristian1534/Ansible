## 1. Setup your development environment

### Repository
- Go to the github repository https://github.com/cristian1534/Ansible.git
- Clone the repository

### Application
- Go to folder `hello-world`
- Run `npm install` .
- Run `npm test` . All tests need to pass.
- Run `npm start` to run the application.
- Check http://localhost:3000 is reachable and displaying "Hello World!"
![React Hello-World localhost 3000](https://ibb.co/gZXVBD8 "React Hello-World localhost 3000")

## 2. Containerize the application
- Using docker, containerize the application.
![Image created by Docker](https://ibb.co/xCLpkzF "Image created by Docker")
- Build the container and run it to make the application available on http://localhost:3000
![Image built and running on port 3000](https://ibb.co/rtkgqcC "Image built and running on port 3000")

## 3. Create a CI Pipeline 
- Create a CI pipeline which 
     - will trigger on push and on pull request
     - Run the tests
     - Only if tests are success, build the container
![Pipeline Github Actions](https://ibb.co/MhRm1JP "Pipeline Github Actions")

> This pipeline upon either a push or pull request generate an action where after passing tests will build a docker image and also will push the image to my personal account in Docker Hub keeping updated the one. Persona Account --> cristianmachuca 

![Image pushed to Docker Hub](https://ibb.co/yNC8cjP "Trigger in Github actions")

## 4. Update "Hello World!" to "Hello DevOps!"
- Update the node js application to display "Hello DevOps!" instead of "Hello World!" using ansible.
> Once you have cloned the repository and updated dependencies. 
- Go to folder `hello-world`
- Run  `sudo ansible-playbook hello-world.playbook.yml`
![Running Ansible to update data on render](https://ibb.co/5B01qn5 "Running Ansible to update data on render")
> - Go to folder `/home` and you will see a new folder cloned called hello-world. But in this case the clone was passing through some steps to update the data to render by React --> "Hello DevOps!" instead "Hello World!".  Ansible has followed these steps:
- clone repository from Github.
- replace the string by using module INLINEFILE.
- update the test file to assert the new string by using module INLINEFILE.
- run the new test to build the docker image.
- build the docker image.-
- build and run the container on port 3000

![Data update by Ansible ](https://ibb.co/5B01qn5 "Data update by Ansible ")

> Now we got to update the render data to 'Hello DevOPs!" by using Ansible.

![React rendering the new data](https://ibb.co/NSwQgMy "React rendering the new data")



## Student
- Cristian Machuca
- cmachuca32@gmail.com