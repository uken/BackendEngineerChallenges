# Backend Engineer Challenges

## Question 1

### Challenge A

Write code to set 100K records in redis as fast as possible (generating a Redis protocol file is not accepted).
 - This operation should repeat every 1 minute
 - Your code will be benchmarked against a redis instance in a different continent than where your application will run
 - A nonoptimal solution is provided in [this file](src/main/java/com/uken/platform/interview/problem1/RedisService.java)

### Challenge B

Write code that maximizes the throughput of writing key value pairs to Redis.

 - A nonoptimal solution is provided in [this file](src/main/java/com/uken/platform/interview/problem2/RedisController.java). This solution will hit a max throughput (e.g.: 2K requests per second) that is not optimal. If the communication between the application and redis is understood and bottlenecks are identified a different solution could be devised that would increase throughput on the same hardware.
 - Throughput can be measured by using a command such as `wrk -c 20 -d 5 -t 2 http://host:8080/pair/key/value`. You will probably need to tweak these values
 - Your code will be benchmarked against a redis instance in a different continent than where your application will run

#### Notes ####
- Challenge A and Challenge B are sharing the same repo for convenience but they are independent Challenges.
- Write a short explanation of why your solution improves on the provided sample solutions.
- You can use different frameworks to solve the problems, but scripted solutions (e.g.: Bash script that generates redis protocol file for mass insertion) will not be accepted.
- We are not looking for infrastructure related solutions (e.g.: Adding more hardware, changing redis server location and etc).

#### Bonus ####
- Make a docker image with your solution

## Question 2

You are tasked with creating a pipeline of user generated events. Each event is represented as a simple ~1KB JSON object, which includes a timestamp and a user_id. Currently, the events take 1TB of disk space and they are growing at a rate of 4,000 events per second. Each user can generate thousands of events. How would you design a low maintenance system with the following specs:
 - Allows for quick retrieval (<10ms) of a single user’s last 100 events at a rate of 1000ops/sec
 - Allows for data to be processed both in batch and in real time
 - How can you make the system reliable?
 - How can you ensure the system will scale?

## Question 3

Write a program that will subtract one list of time ranges from another. Formally: for two
lists of time ranges A and B, a time is in (A-B) if and only if it is part of A and not part of B.

A time range has a start time and an end time. You can define times and time ranges
however you want (Unix timestamps, date/time objects in your preferred language, the
actual string “start-end”, etc).

Your solution shouldn’t rely on the granularity of the timestamps (so don’t, for example, iterate over all the times in all the ranges and check to see if that time is “in”).

Examples:

 - (9:00-10:00) “minus” (9:00-9:30) = (9:30-10:00)
 - (9:00-10:00) “minus” (9:00-10:00) = ()
 - (9:00-9:30) “minus” (9:30-15:00) = (9:00-9:30)
 - (9:00-9:30, 10:00-10:30) “minus” (9:15-10:15) = (9:00-9:15, 10:15-10:30)
 - (9:00-11:00, 13:00-15:00) “minus” (9:00-9:15, 10:00-10:15, 12:30-16:00) = (9:15-10:00, 10:15-11:00)
