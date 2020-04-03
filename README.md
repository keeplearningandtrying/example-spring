# JobRunr example

This repository shows an example how you can integrate JobRunr with [spring.io](https://spring.io/).

## About this project
This project exists out of 3 modules:
- **core**: this project contains [MyService](), a simple spring service with two example methods which you want to run in a backgroundserver  
- **processingapp**: this app is a Spring Console application and runs indefinitely. It polls for new background jobs and processes them when they arrive.  
- **webapp**: this is a Spring Rest Webapp that enqueues new background jobs. 

## How to run this project:
- clone the project and open it in your favorite IDE that supports gradle
- Run the main method from the [WebApplication]() in the `webapp` module and keep it running
- Run the main method from the [JobServerApplication]() in the `processingapp` module and also keep it running
- Open your favorite browser:
  - Navigate to the JobRunr dashboard located at http://localhost:8000/dashboard. This is running within the [JobServerApplication]() as it defines a bean of type [JobRunrDashboardWebServer]()
  - To enqueue a simple job, open a new tab and go to http://localhost:8080/simple-job?name=your-name
  - To enqueue a long running job, open a new tab and go to http://localhost:8080/long-running-job?name=your-name