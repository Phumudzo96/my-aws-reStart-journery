# **Organizing Data**

### **Objective**

Learn how to group and analyze relational database records using the **GROUP BY** and **OVER** clauses with aggregate and ranking functions.

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

✅ Queried the `country` table to view schema and rows:

```sql
SELECT * FROM world.country;
```

---

**1️⃣ Filtering & Ordering Results**

```sql
SELECT Region, Name, Population
FROM world.country
WHERE Region = 'Australia and New Zealand'
ORDER BY Population DESC;
```

---

**2️⃣ Aggregating Data with GROUP BY + SUM()**

```sql
SELECT Region, SUM(Population)
FROM world.country
WHERE Region = 'Australia and New Zealand'
GROUP BY Region
ORDER BY SUM(Population) DESC;
```

---

**3️⃣ Running Totals with OVER() + SUM()**

```sql
SELECT Region, Name, Population,
       SUM(Population) OVER(PARTITION BY Region ORDER BY Population) AS 'Running Total'
FROM world.country
WHERE Region = 'Australia and New Zealand';
```

---

**4️⃣ Ranking Results with OVER() + RANK()**

```sql
SELECT Region, Name, Population,
       SUM(Population) OVER(PARTITION BY Region ORDER BY Population) AS 'Running Total',
       RANK() OVER(PARTITION BY Region ORDER BY Population) AS 'Ranked'
FROM world.country
WHERE Region = 'Australia and New Zealand';
```

---

### **Challenges**

❌ Remembering correct syntax for **window functions** with `PARTITION BY` and `ORDER BY`.

✅ Solved by reviewing MySQL function reference and testing queries incrementally.

---

### **Takeaways**

* **GROUP BY** organizes results into logical sets for aggregation.
* **SUM()** can be used both with `GROUP BY` and as a window function.
* **OVER()** allows calculations across partitions without collapsing rows.
* **RANK()** assigns a position to each row within a partition.
* Combining **aggregate functions** and **window functions** makes SQL a powerful analysis tool.
