# Redis Backend Coding Challenge

## Problem 1

Write code to set 100 thousand records in redis as fast as possible, without using Redis protocol.
 - This operation should repeat every 1 minute.
 - Your code will be benchmarked against a redis instance in a different continent than the code.
 - A nonoptimal solution is provided in [this file](src/main/java/com/uken/platform/interview/problem1/RedisService.java)

## Problem 2

Write code that maximizes the throughput of writing key value pairs to Redis.

 - A nonoptimal solution is provided in [this file](src/main/java/com/uken/platform/interview/problem2/RedisController.java). This solution will max the CPU usage of the server running it but the throughput (e.g.: 10K requests per second) is not optimal and the problem is to increase this number.
 - Your code will be benchmarked against a redis instance in a different continent than the code.
