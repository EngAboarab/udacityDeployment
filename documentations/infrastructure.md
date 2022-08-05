# Infrastructure
-----

The App use the following infrastructure:

- ## front End App : 
``` 
    - Angular 
    - typescript
    - jasmine
```
- ## Back End App:
```
    - Express : for server
    - postgreSQL: for database
    - Typescript
    - sequelize
    - mocha: for testin
```
- ## AWS Services:
```
    - RDS : database hosting
    - S3 : static website hosting
    - Elastic Beanstalk : for API hosting
    - IAM
```

- ## CI/CD tools:
```
    - circleCi
```
----
## Workflow
will decribe the workflow since the user inter the URL in his browser till the showing up of the website

### steps:
1. the user enter the URL in his browser
2. the front end shall communicate with the backend (server)side (via request)
3. the server side shall communicate the database(via query)
4. the database shall respond with the requested data 
5. the server will respond to the front end with the data
6. the browser shall render the data as designed.

---
## Diagram
[link](https://github.com/EngAboarab/udacityDeployment/blob/master/diagrams/Udagram%20Architecture%20Diagram%20.png)