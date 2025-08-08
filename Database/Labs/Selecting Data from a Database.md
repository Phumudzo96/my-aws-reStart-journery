# Selecting Data from a Database

### **Objective**

Learn how to use the **SELECT** statement and common database operators to query data from a relational database.

---

### **Steps Taken**

✅ Connected to the **Command Host** using **Session Manager** in the AWS Console
✅ Switched to the correct directory and accessed the MySQL client:

```bash
sudo su
cd /home/ec2-user/
mysql -u root --password='re:St@rt!9'
```

✅ Verified available databases:

```sql
SHOW DATABASES;
```

✅ Queried all data from the `country` table:

```sql
SELECT * FROM world.country;
```

✅ Counted rows in the `country` table:

```sql
SELECT COUNT(*) FROM world.country;
```

✅ Listed the table schema:

```sql
SHOW COLUMNS FROM world.country;
```

✅ Queried specific columns:

```sql
SELECT Name, Capital, Region, SurfaceArea, Population 
FROM world.country;
```

✅ Added descriptive column alias:

```sql
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country;
```

✅ Ordered results by population:

```sql
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country 
ORDER BY Population;
```

✅ Ordered results by population (descending):

```sql
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country 
ORDER BY Population DESC;
```

✅ Filtered results using `WHERE`:

```sql
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country 
WHERE Population > 50000000 
ORDER BY Population DESC;
```

✅ Combined multiple conditions with `AND`:

```sql
SELECT Name, Capital, Region, SurfaceArea AS "Surface Area", Population 
FROM world.country 
WHERE Population > 50000000 AND Population < 100000000 
ORDER BY Population DESC;
```

---

### **Challenges**

❌ Remembering exact SQL syntax for ordering and filtering data.

✅ Solved by reviewing MySQL documentation and testing queries incrementally.

---

### **Takeaways**

* **SELECT** is the foundation for retrieving data from a database.
* Operators like `<`, `>`, `=`, `WHERE`, `ORDER BY`, and `AND` allow precise data filtering.
* Using **aliases** (`AS`) makes query output more readable.
* Counting rows with **COUNT()** is useful for quick data insights.
