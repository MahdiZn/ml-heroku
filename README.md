# DEPLOY EN HEROKU WIRH DOCKER 

- See Makefile you have all steps 
- create a variable environmnet(kaggle keys,kaggle username ,heroku key ,heroku appname) in your ci/cd ,eg circleci or github worklows etc ..
- if ypu don't have a model pakaged from gemfurry you can add it in your files and requirements
- first build image from directory when you have a Dockerfile  (localy is docker build -t name-image:tag . ) 
- IF YOU WAN RUN docker LOCALY YOU HAVE TU PASS port (docker run --rm -p 8001:8001 -e PORT=8001 name-image)
