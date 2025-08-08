# **Performing a Conditional Search**

### **Objective**

Learn how to use the **SELECT** statement with a **WHERE** clause to filter records using conditions, ranges, patterns, and functions.

---

### **Steps Taken**

✅ Connected to **Command Host** via AWS Session Manager

```bash
sudo su
cd /home/ec2-user/
mysql -u root --password='re:St@rt!9'
```

✅ Verified `world` database exists:

```sql
SHOW DATABASES;
```

✅ Queried all countries:

```sql
SELECT * FROM world.country;
```

---

**1️⃣ Filter with AND & Comparison Operators**

```sql
SELECT Name, Capital, Region, SurfaceArea, Population
FROM world.country
WHERE Population >= 50000000 AND Population <= 100000000;
```

---

**2️⃣ Filter with BETWEEN**

```sql
SELECT Name, Capital, Region, SurfaceArea, Population
FROM world.country
WHERE Population BETWEEN 50000000 AND 100000000;
```

---

**3️⃣ Pattern Matching with LIKE & Aggregate with SUM**

```sql
SELECT SUM(Population)
FROM world.country
WHERE Region LIKE "%Europe%";
```

---

**4️⃣ Use Column Aliases**

```sql
SELECT SUM(Population) AS "Europe Population Total"
FROM world.country
WHERE Region LIKE "%Europe%";
```

---

**5️⃣ Case-Insensitive Matching with LOWER**

```sql
SELECT Name, Capital, Region, SurfaceArea, Population
FROM world.country
WHERE LOWER(Region) LIKE "%central%";
```

---

### **Challenges**

❌ Remembering when `LIKE` is case-sensitive depending on DB collation.

✅ Solved by using the `LOWER()` function for consistent matching.

---

### **Takeaways**

* **WHERE** filters rows based on conditions.
* **BETWEEN** is more readable for ranges than `>=` and `<=`.
* **LIKE** with `%` enables flexible pattern matching.
* **AS** creates column aliases for clearer output.
* **LOWER** ensures case-insensitive comparisons.
