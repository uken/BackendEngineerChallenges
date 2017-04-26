# Redis Backend Coding Challenge

## Challenge 1

Write code to set 100K records in redis as fast as possible (generating a Redis protocol file is not accepted).
 - This operation should repeat every 1 minute
 - Your code will be benchmarked against a redis instance in a different continent than where your application will run
 - A nonoptimal solution is provided in [this file](src/main/java/com/uken/platform/interview/problem1/RedisService.java)

## Challenge 2

Write code that maximizes the throughput of writing key value pairs to Redis.

 - A nonoptimal solution is provided in [this file](src/main/java/com/uken/platform/interview/problem2/RedisController.java). This solution will max the CPU usage of the server running it but the throughput (e.g.: 2K requests per second) is not optimal and the challenge is to increase this number
 - Throughput can be measured by using a command such as `wrk -c 20 -d 5 -t 2 http://host:8080/pair/key/value`. You will probalby need to tweak these values
 - Your code will be benchmarked against a redis instance in a different continent than where your application will run

### Notes ###
- Challenge1 and Challenge2 are sharing the same repo for convenience but they are independent Challenges.
- Write a short explanation of why your solution improves on the provided sample solutions.
- You can use different frameworks to solve the problems, but scripted solutions (e.g.: Bash script that generates redis protocol file for mass insertion) will not be accepted.
