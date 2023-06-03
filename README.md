**# MySQL
All lab assignment <br>
To login (from unix shell) use -h only if needed - <br>   
[mysql dir]/bin/mysql -h hostname -u root -p <br> 
Create a database on the sql server - create database [databasename];<br> 
List all databases on the sql server - show databases;<br> 
Switch to a database -	use [db name];<br> 
To see all the tables in the db - show tables;<br> 
To see database's field formats - describe [table name];<br> 
To delete a db - drop database [database name];<br> 
To delete a table - drop table [table name];<br> 
Show all data in a table - SELECT * FROM [table name];<br> 
Returns the columns and column information pertaining to the designated table - show columns from [table name];<br> 	
Show certain selected rows with the value "whatever" - SELECT * FROM [table name] WHERE [field name] = "whatever";	<br> 
Show all records containing the name "Bob" AND the phone number '3444444' - 	SELECT * FROM [table name] WHERE name = "Bob" AND phone_number = '3444444';	<br> 
Show all records not containing the name "Bob" AND the phone number '3444444' order by the phone_number field -	SELECT * FROM [table name] WHERE name != "Bob" AND phone_number = '3444444' order by phone_number;	<br> 
Show all records starting with the letters 'bob' AND the phone number '3444444'	 - SELECT * FROM [table name] WHERE name like "Bob%" AND phone_number = '3444444';	<br> 
Use a regular expression to find records. Use "REGEXP BINARY" to force case-sensitivity. This finds any record beginning with a -	SELECT * FROM [table name] WHERE rec RLIKE "^a$";	<br> 
Show unique records -	SELECT DISTINCT [column name] FROM [table name];<br> 
Show selected records sorted in an ascending (asc) or descending (desc) - SELECT [col1],[col2] FROM [table name] ORDER BY [col2] DESC;
Count rows.	SELECT COUNT(*) FROM [table name];	<br> 
Join tables on common columns -	select lookup.illustrationid, lookup.personid,person.birthday from lookup<br> 
left join person on lookup.personid=person.personid=statement to join birthday in person table with primary illustration id;<br> 
Switch to the mysql db -  Create a new user.	INSERT INTO [table name] (Host,User,Password) VALUES('%','user',PASSWORD('password'));<br> 
Change a users password.(from unix shell) - [mysql dir]/bin/mysqladmin -u root -h hostname.blah.org -p password 'new-password'<br> 
Change a users password.(from MySQL prompt) - SET PASSWORD FOR 'user'@'hostname' = PASSWORD('passwordhere');<br> 
Switch to mysql db.Give user privilages for a db - INSERT INTO [table name] <br> (Host,Db,User,Select_priv,Insert_priv,Update_priv,Delete_priv,Create_priv,Drop_priv) VALUES ('%','db','user','Y','Y','Y','Y','Y','N');
To update info already in a table.	UPDATE [table name] SET Select_priv = 'Y',Insert_priv = 'Y',Update_priv = 'Y' where [field name] = 'user';<br> 
Delete a row(s) from a table - DELETE from [table name] where [field name] = 'whatever';<br> 
Update database permissions/privilages - FLUSH PRIVILEGES;<br> 
Delete a column - alter table [table name] drop column [column name];<br> 
Add a new column to db - alter table [table name] add column [new column name] varchar (20);<br> 
Change column name - alter table [table name] change [old column name] [new column name] varchar (50);<br> 
Make a unique column so you get no dupes - alter table [table name] add unique ([column name]);<br> 
Make a column bigger - alter table [table name] modify [column name] VARCHAR(3);<br> 
Delete unique from table - alter table [table name] drop index [colmn name];<br> 
Load a CSV file into a table - LOAD DATA INFILE '/tmp/filename.csv' replace INTO TABLE [table name] FIELDS TERMINATED BY ',' LINES TERMINATED BY '\n' (field1,field2,field3);<br> 
Dump all databases for backup - Backup file is sql commands to recreate all db's -	[mysql dir]/bin/mysqldump -u root -ppassword --opt >/tmp/alldatabases.sql<br> 
Dump one database for backup -	[mysql dir]/bin/mysqldump -u username -ppassword --databases databasename >/tmp/databasename.sql<br> 
Dump a table from a database - [mysql dir]/bin/mysqldump -c -u username -ppassword databasename tablename > /tmp/databasename.tablename.sql<br> 
Restore database (or database table) from backup - [mysql dir]/bin/mysql -u username -ppassword databasename < /tmp/databasename.sql<br>
Create Table Example 1.	CREATE TABLE [table name] (firstname VARCHAR(20), middleinitial VARCHAR(3), lastname VARCHAR(35),suffix VARCHAR(3),
officeid VARCHAR(10),userid VARCHAR(15),username VARCHAR(8),email VARCHAR(35),phone VARCHAR(25), groups
VARCHAR(15),datestamp DATE,timestamp time,pgpemail VARCHAR(255));<br> 
Create Table Example 2.	create table [table name] (personid int(50) not null auto_increment primary key,firstname varchar(35),middlename varchar(50),lastname varchar(50) default 'bato');<br> **
