# **Working with Functions**

### **Objective**

Learn how to use common SQL functions with the **SELECT** statement and **WHERE** clause to manipulate, filter, and summarize data.

---

### **Steps Taken**

✅ Connected to **Command Host** via AWS Session Manager

```bash
sudo su
cd /home/ec2-user/
mysql -u root --password='re:St@rt!9'
```

✅ Verified the `world` database exists:

```sql
SHOW DATABASES;
```

✅ Queried all countries:

```sql
SELECT * FROM world.country;
```

---

**1️⃣ Aggregate Functions (SUM, AVG, MAX, MIN, COUNT)**

```sql
SELECT SUM(Population), AVG(Population), MAX(Population), MIN(Population), COUNT(Population)
FROM world.country;
```

---

**2️⃣ Splitting Strings with SUBSTRING\_INDEX**

```sql
SELECT Region, SUBSTRING_INDEX(Region, " ", 1)
FROM world.country;
```

---

**3️⃣ Filtering with SUBSTRING\_INDEX in WHERE**

```sql
SELECT Name, Region
FROM world.country
WHERE SUBSTRING_INDEX(Region, " ", 1) = "Southern";
```

---

**4️⃣ Length-Based Filtering with LENGTH & TRIM**

```sql
SELECT Region
FROM world.country
WHERE LENGTH(TRIM(Region)) < 10;
```

---

**5️⃣ Removing Duplicates with DISTINCT**

```sql
SELECT DISTINCT(Region)
FROM world.country
WHERE LENGTH(TRIM(Region)) < 10;
```

---

### **Challenges**

❌ Remembering exact syntax for `SUBSTRING_INDEX` when splitting strings.

✅ Solved by reviewing MySQL documentation and testing queries step-by-step.

---

### **Takeaways**

* **Aggregate functions** (SUM, AVG, MAX, MIN, COUNT) help summarize datasets quickly.
* **SUBSTRING\_INDEX** can extract specific parts of a string for filtering or display.
* **LENGTH** and **TRIM** are useful for checking string sizes while ignoring extra spaces.
* **DISTINCT** removes duplicate results for cleaner outputs.
* Functions can be used in both **SELECT** and **WHERE** clauses for powerful queries.
