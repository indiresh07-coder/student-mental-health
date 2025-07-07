# Student Mental Health SQL Analysis

This project explores how living arrangements affect mental health outcomes for international students, based on a dataset from a DataCamp project.

## 📌 Objective
To analyze whether students' living conditions correlate with levels of depression, self-concept, and anxiety.

## 🧠 SQL Query Summary

The query groups international students (`inter_dom = 'Inter'`) by their living arrangement (`stay`) and calculates:
- `COUNT(*)`: Number of students in each group
- `AVG(todep)`: Average PHQ depression score
- `AVG(tosc)`: Average Self-Concept Scale score
- `AVG(toas)`: Average Anxiety Scale score

### Sample Query Used

```sql
SELECT stay, 
       COUNT(*) AS count_int,
       ROUND(AVG(todep), 2) AS average_phq, 
       ROUND(AVG(tosc), 2) AS average_scs, 
       ROUND(AVG(toas), 2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
