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



