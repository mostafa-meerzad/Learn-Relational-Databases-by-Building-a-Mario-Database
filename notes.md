# Learn Relational Databases by Building a Mario Database

1. Your virtual machine comes with PostgreSQL installed. You will use the Psql terminal application to interact with it. Log in by typing `psql --username=freecodecamp --dbname=postgres` into the terminal and pressing enter.
2. Notice that the prompt changed to let you know that you are now interacting with PostgreSQL. First thing to do is see what databases are here. Type \l into the prompt to list them.
3. The databases you see are there by default. You can make your own like this:
   `CREATE DATABASE database_name;`
   The capitalized words are keywords telling PostgreSQL what to do. The name of the database is the lowercase word. **Note that all commands need a semi-colon at the end**. Create a new database named **first_database**.
4. It worked. Your new database is there. If you don't get a message after entering a command, it means it's incomplete and you likely forgot the **semi-colon**. You can just add it on the next line and press enter to finish the command. Create another database named **second_database**
5. You can connect to a database by entering `\c database_name`. You need to connect to add information. Connect to your second_database.
6. You should see a message that you are connected. Notice that the prompt changed to **second_database=>**. So the **postgres=>** prompt before must have meant you were connected to that database. A database is made of tables that hold your data. Enter `\d` to **display** the tables.
7. Looks like there's no tables or relations yet. Similar to how you created a database, you can create a table like this:
   `CREATE TABLE table_name();`
   Note that the **parenthesis** are needed for this one. It will create the **table** in the database you are connected to. Create a table named first_table in second_database.
8. You can view more details about a table by adding the table name after the display command like this:` \d table_name`. View more details about your second_table.
9. Tables need **columns** to describe the data in them, yours doesn't have any yet. Here's an example of how to add one:
   `ALTER TABLE table_name ADD COLUMN column_name DATATYPE;`
   Add a column to second_table named first_column. Give it a data type of **INT**. **INT** stands for integer. Don't forget the semi-colon.
10. Your column is there 😄 Use `ALTER TABLE` and `ADD COLUMN` to add another column to **second_table** named id that's a type of **INT**.
11. Your table should have an id column added. View the details of second_table to make sure.
12. Those are some good looking columns. You will probably need to know how to remove them. Here's an example:
    `ALTER TABLE table_name DROP COLUMN column_name;`
    Drop your age column.
13. A common data type is `VARCHAR`. It's a short string of characters. You need to give it a maximum length when using it like this: `VARCHAR(30)`.

14. Add a new column to **second_table**, give it a name of **name** and a data type of **VARCHAR(30)**.
15. You can see the **VARCHAR** type there. The **30** means the data in it can be a max of 30 characters. You named that column **name**, it should have been username. Here's how you can rename a column:
    `ALTER TABLE table_name RENAME COLUMN column_name TO new_name`;
    Rename the name column to username.
16. It worked. Rows are the actual data in the table. You can add one like this:
    `INSERT INTO table_name(column_1, column_2) VALUES(value1, value2);`
    **Insert** a row into **second_table**. Give it an **id** of **1**, and a **username** of **Samus**. The username column expects a **VARCHAR**, so you need to put **Samus** in single quotes like this: `'Samus'`.

17. You should have one row in your table. You can view the data in a table by querying it with the **SELECT** statement. Here's how it looks:
    `SELECT columns FROM table_name;`
    Use a SELECT statement to view all the columns in second_table. Use an asterisk (\*) to denote that you want to see all the columns.
18. There's your one row. **Insert** another row into **second_table**. Fill in the id and username columns with the values **2** and **'Mario'**.
19. Insert another row into second_table. Use 3 as the id, and Luigi as the username this time.
20. That gives me an idea 😃 You can make a database of **Mario** video game characters. You should start from scratch for it. Why don't you delete the record you just entered. Here's an example of how to delete a row:`DELETE FROM table_name WHERE condition;`
    Remove Luigi from your table. The condition you want to use is username='Luigi'
21. It's gone. You can scrap all this for the new database. Delete Mario from second_table using the same command as before, except make the condition username='Mario' this time.
22. Looks like they're all gone. Remind yourself what columns you have in second_table by looking at its details.
23. There's two columns. You won't need either of them for the Mario database. Alter the table second_table and drop the column username.
24. Okay, the table has no rows or columns left. View the tables in this database to see what is here.
    1. Use the display shortcut command
25. Still two. You won't need either of those for the new database either. Drop second_table from your database. Here's an example: `DROP TABLE table_name;`
26. Rename first_database to mario_database. You can rename a database like this: `ALTER DATABASE database_name RENAME TO new_database_name;`
27. Now that you aren't connected to second_database, you can drop it. Use the `DROP DATABASE` keywords to do that.
28. Okay, I think you're ready to get started. I don't think you created any tables here, take a look to make sure.
29. Create a new table named characters, it will hold some basic information about Mario characters
30. 
