- 👋 Hi, I’m @Chakkz0206
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Chakkz0206/Chakkz0206 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
1. Provide a list of 5 platforms with the least number of projects available.
```SQL
SELECT platform, count(name) as `Number of Projects`
FROM `bigquery-public-data.libraries_io.projects` 
Group by 1 
Order by 2 ASC
LIMIT 5
```
![image](https://github.com/Chakkz0206/Chakkz0206/assets/131430244/79541313-30e7-4bbe-abe7-350c548fe56b)

2. Provide a list of 5 languages with the most number of projects available.
```SQL
SELECT language, count(name) as `Number of Projects`
FROM `bigquery-public-data.libraries_io.projects` 
Group by 1 
Order by 2 DESC
LIMIT 5
```
![image](https://github.com/Chakkz0206/Chakkz0206/assets/131430244/d4d2cf8c-393e-403a-9688-c95a88c02cb0)

3. What is the minimum, maximum and average repository size?
```SQL
SELECT Min (repository_size) as `Minimum Size`, Max(repository_size) as `Maximum Size`, avg (repository_size) as`Average Size`
FROM `bigquery-public-data.libraries_io.projects_with_repository_fields`
```
![image](https://github.com/Chakkz0206/Chakkz0206/assets/131430244/d7deecda-7ad3-4651-b692-93941f46ca02)

4. What is the maximum and average repository size in different platforms?
```SQL
SELECT platform, Max(repository_size) as `Maximum Size`, avg (repository_size) as`Average Size`
FROM `bigquery-public-data.libraries_io.projects_with_repository_fields`
Group by 1
```
![image](https://github.com/Chakkz0206/Chakkz0206/assets/131430244/c680dd2b-0c06-459a-864e-0f86c4556db5)
 


