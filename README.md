
# Udagram

 This project  is a deploying of full-stack website on AWS witht the using of CircleCI as CI/CD tool. The udagram application is a fairly simple application that includes all the major components of a Full-Stack web application and was built over a provided starter project which you could find via [starter project link](https://github.com/udacity/nd0067-c4-deployment-process-project-starter).

the link for the working website is [udagram-api](http://udagramfront.s3-website-us-east-1.amazonaws.com)

## screenshots :
for the successful deploy and circleCI is [here](https://github.com/EngAboarab/udacityDeployment/tree/master/screenshots)

### Dependencies

```
- Node v14.15.1 (LTS) or more recent. While older versions can work it is advisable to keep node to latest LTS version

- npm 6.14.8 (LTS) or more recent, Yarn can work but was not tested for this project

- AWS CLI v2, v1 can work but was not tested for this project

- A RDS database running Postgres.

- A S3 bucket for hosting uploaded pictures.
 

```
 A list of dependencies for both back and front end you can find in dependencies.md](https://github.com/EngAboarab/udacityDeployment/tree/master/documentations/dependencies.md).

## Infrastructure
[infrastructure.md](https://github.com/EngAboarab/udacityDeployment/blob/master/documentations/infrastructure.md) 

## Instructions 
-----

### - Installation


1. install the nccessary dependencies 
```npm run frontend:install
   npm run api:install
``` 

2. inside the backend(udagram-api) create your .env file reference to [ENV_Example file](https://github.com/EngAboarab/udacityDeployment/blob/master/ENV_Example)  

**note** __make sure to let the port value blank__



### - depolyment:
----
via AWS Console execute the following:
1. create the required database via AWS RDS and make sure to make the DB public
2. update the .env variable accordingly.

3. in the EB create a new environment (with sample application at first)and deploy the backend on it :
```
   - udate the name of the env in backend json file 
   "deploy": "npm run build && eb list && eb use __Udagramapi-env__ && eb deploy",

   npm run api:deploy
```

4. set the enviroment properties on EB configration with the (POSTGRES_USERNAME,POSTGRES_PASSWORD,POSTGRES_DB ,PORT,DB_PORT,POSTGRES_HOST)

5. in the front end (udagram-frontend/environments) change the apiHost value to the link of you eb env. 'http://yourlink/api/v0' in both files  

**note:** __do not forget /api/v0 portion

6. in AWS S3 create a New Bucket and **make sure make the acls enabled and make it public and enable static website hosting and finally change the bucket policy**

7. in the front end (udagram-frontend/bin/deploy.sh) update the link for your bucket aws s3 cp --recursive --acl public-read ./www s3://__udagramfront/__

8. deploy the front end to aws bucket 
``` npm run frontend:deploy```


### CI/CD using CicleCI:
1. push your project to you github account

2. open your circleCI account
3. add a new project /select you repo
4. in the project setting/Enviromental Variables  add AWS_ACCESS_KEY_ID AWS_DEFAULT_REGION AWS_SECRET_ACCESS_KEY
5. rebuild your project




## Built With
----

- [Angular](https://angular.io/) - Single Page Application Framework
- [Node](https://nodejs.org) - Javascript Runtime
- [Express](https://expressjs.com/) - Javascript API Framework

