# Pipeline Porcess
----

I have use CircleCi as the CI/CD tool 


## workflow
 we will list the steps between the developer change the code til the reflection on the website

    ### steps:
    
        1.The developer has committed changes in his code  
        ```git commit -m "xxx"```
        2. the developer has pushed to the repo.
        ```git push -f origin BRANCH_NAMAE```
        3. the circleCi will sense the changes
        4. the circleCi will rebuild the project
        5. the circleCi will update the website autmoatically


## Diagram
[link](https://github.com/EngAboarab/udacityDeployment/blob/master/diagrams/pipeline.png)