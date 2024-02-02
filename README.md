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

3. What is the minimum, maximum, and average repository size?
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

5. Provide the number of projects for source ranks from 10 to 20. 
```SQL
SELECT count (name) as `Number of Projects`, sourcerank FROM `bigquery-public-data.libraries_io.projects`
Where sourcerank between 10 and 20
group by 2
```
![image](https://github.com/Chakkz0206/Chakkz0206/assets/131430244/36fb819d-2baa-4922-a63d-134ae5f1b464)

6. Provide a list of the top 10 projects which has the highest number of dependent repositories
```SQL
SELECT name, count(dependent_repositories_count) as `Number of Dependent Repositories` FROM `bigquery-public-data.libraries_io.projects` 
GROUP BY name
ORDER BY count(dependent_repositories_count) DESC
LIMIT 10
```
![image](https://github.com/Chakkz0206/Chakkz0206/assets/131430244/43082c1f-01d2-4ed3-a3a4-85b59d91dbc4)

7. Provide a list of repository name with owner with repository id between 5000 and 6000, who has published the project with repository in the platform Dub.
```SQL
SELECT p.platform, pr.repository_id,pr.repository_name_with_owner
FROM `bigquery-public-data.libraries_io.projects` p
Left join `bigquery-public-data.libraries_io.projects_with_repository_fields` pr
on p.repository_id = pr.repository_id
WHERE p.platform = "Dub" and p.repository_id BETWEEN 5000 and 6000
```
![image](https://github.com/Chakkz0206/Chakkz0206/assets/131430244/22ee4961-cfab-4c84-ad3b-9bf07b8b7cdd)

8. Provide a list of 100 entries in the ascending order of repository id, with name of the project unique by Platform,which is hosted on Github
```SQL
SELECT pr.repository_id,p.name,pr.repository_host_type
FROM `bigquery-public-data.libraries_io.projects` p
Inner join `bigquery-public-data.libraries_io.projects_with_repository_fields` pr
on p.repository_id = pr.repository_id 
WHERE pr.repository_host_type = "GitHub"
ORDER BY 1 ASC
LIMIT 100
```
![image](https://github.com/Chakkz0206/Chakkz0206/assets/131430244/b8e936f4-53a4-4ec3-9ef9-c3069cae98bc)

9. Find out the total size of all the repositories hosted by different platforms and list it down in descending order.
```SQL
With Projects as 
(SELECT p.platform, pr.repository_id, pr.repository_size
FROM `bigquery-public-data.libraries_io.projects` p
Left join `bigquery-public-data.libraries_io.projects_with_repository_fields` pr
on p.repository_id = pr.repository_id)
SELECT platform, Sum(repository_size) as `Total size of repositories` from Projects
GROUP BY platform 
Order BY Sum(repository_size) DESC
```
![image](https://github.com/Chakkz0206/Chakkz0206/assets/131430244/64f1d0f2-b902-4ad1-b82e-fdc6fb777d09)



