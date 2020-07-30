Docker development and deployment of react app

1. install docker if you have linux you must install docker-compose

2. CI/CD pipeline

    - git clone repository
    - in CMD on Windows or terminal in linux or Mac navigate to clone repo folder on your local machine
    - in your prefered code editor, open your project folder and make a change in your docker-compose.yml file set the 

    
            volumes:
              - /app/node_modules
              - your_project_folder_path:/app


    - in terminal or CMD, execute command docker-compose up 
    - in browser type in URL localhost:3000



    - then make a change in your code and see the 
    changes automagicaly take afect in the browser, this is achived with docker volumes in docker-compose.yml file
    (of course if everything is working as it should :) )

3. issues

    - in the github actions workflows build, the github actions will not execute the docker -it flag command
    the error is "the input device is not a 
    TTY", it is located in Acitons commit Docker_React_Test_1.0.5, because the docker react app will not run without that -it flag,
    the whole raw docker command looks like this " docker run -it -p 3000:3000 image name or id " 

    - the docker -it flag is set in docker-compose.yml thats why it works on local machine, and not on Github Actions

            (-it flag == stdin_open: true
                         tty: true)

    in docker-compose.yml



Made by Blaž
