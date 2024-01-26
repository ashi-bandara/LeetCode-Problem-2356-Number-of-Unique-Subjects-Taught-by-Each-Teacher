
# LeetCode Challenge D41
## Achievements
[![image.png](https://i.postimg.cc/tR5RX1cz/image.png)](https://postimg.cc/Hjr1zLdJ)

This solution outperformed 97.86% of Java users on LeetCode according to runtime metrics.

## Overview

Welcome to my LeetCode solution repository! This project addresses the coding challenge presented by [2356. Number of Unique Subjects Taught by Each Teacher](https://leetcode.com/problems/number-of-unique-subjects-taught-by-each-teacher/). Below, you'll find details about the problem, my approach to solving it, and the implemented solution.

## Problem Statement
Table:  `Teacher`
| Column Name | Type |
|:-----------:|:----:|
|  teacher_id |  int |
|  subject_id |  int |
|   dept_id   |  int |

> (subject_id, dept_id) is the primary key (combinations of columns with unique values) of this table. Each row in this table indicates that the teacher with teacher_id teaches the subject subject_id in the department dept_id.

Write a solution to calculate the number of unique subjects each teacher teaches in the university.
Return the result table in  **any order**.
The result format is shown in the following example

**Example**
> **Input:** 

| teacher_id | subject_id | dept_id |
|:----------:|:----------:|:-------:|
|      1     |      2     |    3    |
|      1     |      2     |    4    |
|      1     |      3     |    3    |
|      2     |      1     |    1    |
|      2     |      2     |    1    |
|      2     |      3     |    1    |
|      2     |      4     |    1    |

>**Output:** 

| teacher_id | cnt |
|:----------:|:---:|
|      1     |  2  |
|      2     |  4  |

>**Explanation:**
>
>Teacher 1:
>   - They teach subject 2 in departments 3 and 4.
>   - They teach subject 3 in department 3. 
>   
>Teacher 2:
>   - They teach subject 1 in department 1.
>   - They teach subject 2 in department 1.
>   - They teach subject 3 in department 1.
>   - They teach subject 4 in department 1.

**Language Used**
> MySQL

**Difficulty**
> Easy

## Solution Overview
The query employs the `COUNT(DISTINCT subject_id)` function to calculate the count of distinct subjects for each teacher. The `DISTINCT` keyword ensures that each subject is considered only once for each teacher. The result is then grouped by the `teacher_id` using the `GROUP BY` clause, ensuring that the subsequent count is performed for each unique teacher. The final output of the query includes the teacher's identifier (`teacher_id`) and the count of unique subjects (`cnt`) they teach.
