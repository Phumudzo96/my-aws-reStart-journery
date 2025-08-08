# Insert, Update, and Delete Data in a Database

### **Objective**

Learn how to **insert**, **update**, **delete**, and **import** rows of data using SQL.

---

### **Steps Taken**

✅ Connected to **Command Host** via AWS Session Manager

```bash
sudo su
cd /home/ec2-user/
mysql -u root --password='re:St@rt!9'
```

✅ Verified existing databases:

```sql
SHOW DATABASES;
```

---

**1️⃣ Insert Rows**

```sql
INSERT INTO world.country VALUES 
('IRL','Ireland','Europe','British Islands',70273.00,1921,3775100,76.8,75921.00,73132.00,'Ireland/Éire','Republic',1447,'IE'),
('AUS','Australia','Oceania','Australia and New Zealand',7741220.00,1901,18886000,79.8,351182.00,392911.00,'Australia','Constitutional Monarchy, Federation',135,'AU');
SELECT * FROM world.country WHERE Code IN ('IRL', 'AUS');
```

---

**2️⃣ Update Rows**

```sql
UPDATE world.country SET Population = 0;
UPDATE world.country SET Population = 100, SurfaceArea = 100;
SELECT * FROM world.country;
```

---

**3️⃣ Delete Rows**

```sql
SET FOREIGN_KEY_CHECKS = 0;
DELETE FROM world.country;
SELECT * FROM world.country;
```

---

**4️⃣ Import Data from SQL File**

```bash
QUIT;
ls /home/ec2-user/world.sql
mysql -u root --password='re:St@rt!9' < /home/ec2-user/world.sql
mysql -u root --password='re:St@rt!9'
USE world;
SHOW TABLES;
SELECT * FROM country;
```

---

### **Challenges**

❌ Risk of updating or deleting all rows without a `WHERE` clause.

✅ Solved by testing on lab data and confirming results after each query.

---

### **Takeaways**

* **INSERT** adds new records to a table.
* **UPDATE** changes existing records; use `WHERE` to avoid bulk changes.
* **DELETE** removes records; without `WHERE`, all rows are deleted.
* SQL scripts (`.sql` files) allow bulk data imports efficiently.
