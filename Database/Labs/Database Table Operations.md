## **Database Table Operations**

### **Objective**

Learn how to create, alter, and delete databases and tables in MySQL.

---

### **Steps Taken**

1. **Connected to Command Host** via AWS Session Manager:

   ```bash
   sudo su
   cd /home/ec2-user/
   mysql -u root --password='re:St@rt!9'
   ```
2. **Created Database & Table**

   * `CREATE DATABASE world;`
   * Created `country` table with multiple columns (Code, Name, Continent, Region, etc.)
   * Verified creation with `SHOW DATABASES;` and `SHOW TABLES;`
3. **Reviewed Table Schema**

   * Used `SHOW COLUMNS FROM world.country;`
   * Identified typo in `Conitinent` column.
4. **Altered Table Structure**

   * Corrected column name with:

     ```sql
     ALTER TABLE world.country RENAME COLUMN Conitinent TO Continent;
     ```
5. **Challenge**

   * Created `city` table with `Name` and `Region` columns.
6. **Dropped Tables & Database**

   * Deleted `city` and `country` tables using `DROP TABLE`
   * Deleted `world` database using `DROP DATABASE`

---

### **Challenges**

❌ Misspelled column name in schema (`Conitinent`)

✅ Solved by using `ALTER TABLE ... RENAME COLUMN`

---


### **Takeaways**

* `CREATE DATABASE` and `CREATE TABLE` define data storage structures.
* `SHOW` commands are useful for verifying schema and available databases/tables.
* `ALTER TABLE` can fix column names or change schema without dropping data.
* `DROP` permanently removes tables or databases — no recovery without backups.
* Careful schema review before data entry avoids costly corrections.
