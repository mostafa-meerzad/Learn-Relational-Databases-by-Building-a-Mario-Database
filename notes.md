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
30. Next, you can add some columns to the table. Add a column named **character_id** to your new table that is a type of **SERIAL**.
31. The **SERIAL** type will make your column an **INT** with a **NOT NULL** constraint, and automatically increment the integer when a new row is added. View the details of the characters table to see what SERIAL did for you.
32. Add a column to characters called name. Give it a data type of **VARCHAR(30)**, and a constraint of **NOT NULL**. Add a constraint by putting it right after the data type.
33. You can make another column for where they are from. Add another column named **homeland**. Give it a data type of **VARCHAR** that has a max length of **60**.
34. You are ready to start adding some rows. First is Mario. Earlier, you used this command to add a row:
    `INSERT INTO second_table(id, username) VALUES(1, 'Samus');`
    The first parenthesis is for the column names, you can put as many columns as you want. The second parenthesis is for the values for those columns. Add a row to your table, give it a name of **Mario**, a homeland of **Mushroom Kingdom**, and a favorite_color of **Red**. Make sure to use single quotes where needed.
35. Use `SELECT * FROM characters;` to view that the character_id has changed now.
36. Add another row for Luigi. Give it a name of **Luigi**, a homeland of **Mushroom Kingdom**, and a favorite_color of **Green**.
37. View all the data in your characters table with SELECT again.
38. Adding rows one at a time is quite tedious. Here's an example of how you could have added the previous three rows at once:
    `INSERT INTO characters(name, homeland, favorite_color)
VALUES('Mario', 'Mushroom Kingdom', 'Red'),
('Luigi', 'Mushroom Kingdom', 'Green'),
('Peach', 'Mushroom Kingdom', 'Pink');`
    Add two more rows. Give the first one the values: Toadstool, Mushroom Kingdom, and Red. Give the second one: Bowser, Mushroom Kingdom, and Green. Try to add them with one command.
39. If you don't get a message after a command, it is likely incomplete. This is because you can put a command on multiple lines. Add two more rows. Give the first one the values: Daisy, Sarasaland, and Yellow. The second: Yoshi, Dinosaur Land, and Green. Try to do it with one command.
40. It looks good, but there's a few mistakes. You can change a value like this:
    `UPDATE table_name SET column_name=new_value WHERE condition;`
    You used username='Samus' as a condition earlier. SET Daisy's favorite_color to Orange. You can use the condition name='Daisy' to change her row.
41. The command you just used does exactly what it sounds like. It finds the row where name is Daisy, and sets her favorite_color to Orange. Take a look at all the data in your table again to see if she got updated.
42. Her favorite color was updated. Toadstool's name is wrong as well, it's actually Toad. Use UPDATE to SET his name to Toad. Use the condition favorite_color='Red'.
43. Using favorite_color='Red' was not a good idea. Mario's name changed to Toad because he likes red, and now there's two rows that are the same. Well, almost. Only the character_id is different. You will have to use that to change it back to Mario. Use UPDATE to set the name to Mario for the row with the lowest character_id.
44. Actually, you should put that in order. Here's an example:
    SELECT` columns FROM table_name ORDER BY column_name;`
    View all the data again, but put it in order by character_id.
    1. Try entering SELECT \* FROM characters ORDER BY character_id;
45. It looks good. Next, you are going to add a **primary key**. It's a column that uniquely identifies each row in the table. Here's an example of how to set a PRIMARY KEY:
    `ALTER TABLE table_name ADD PRIMARY KEY(column_name);`
    The name column is pretty unique, why don't you set that as the primary key for this table.
46. You should set a primary key on every table and there can only be one per table. Take a look at the details of your characters table to see the primary key at the bottom.
47. You can see the key for your name column at the bottom. It would have been better to use character_id for the primary key. Here's an example of how to drop a constraint:
    `ALTER TABLE table_name DROP CONSTRAINT constraint_name;`
    Drop the primary key on the name column. You can see the constraint name is characters_pkey.
48. View the details of the characters table to make sure it's gone.
49. That's better. The table looks complete for now. Next, create a new table named more_info for some extra info about the characters.
50. I wonder what that third one is. It says characters_character_id_seq. I think I have a clue. View the details of the characters table
51. That is what finds the next value for the character_id column. Add a column to your new table named more_info_id. Make it a type of SERIAL.
52. Set your new column as the primary key for this table.
53. There it is. Add another column to more_info named birthday. Give it a data type of DATE
54. Add a weight column. Give it a type of **NUMERIC(4, 1)**. That data type is for decimals. **NUMERIC(4, 1)** has up to four digits and one of them has to be to the right of the decimal.
55. There’s your four columns and the primary key you created at the bottom. To know what row is for a character, you need to set a foreign key so you can relate rows from this table to rows from your characters table. Here's an example that creates a column as a foreign key:
    `ALTER TABLE table_name ADD COLUMN column_name DATATYPE REFERENCES referenced_table_name(referenced_column_name);`
    That's quite the command. In the more_info table, create a character_id column. Make it an INT and a foreign key that references the character_id column from the characters table. Good luck.
56. To set a row in more_info for Mario, you just need to set the character_id (foreign key) value to whatever it is in the characters table. Take a look at the details of more_info to see your foreign key.
57. There's your foreign key at the bottom. These tables have a **"one-to-one"** relationship. One row in the **characters** table will be related to exactly one row in **more_info** and vice versa. Enforce that by adding the **UNIQUE** constraint to your foreign key. Here's an example:
    `ALTER TABLE table_name ADD UNIQUE(column_name);`
    Add the UNIQUE constraint to the column you just added.
58. The column should also be **NOT NULL** since you don't want to have a row that is for nobody. Here's an example:
    `ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;`
    Add the NOT NULL constraint to your foreign key column.
59. The structure is set, now you can add some rows. First, you need to know what **character_id** you need for the **foreign key column**.
60. You have viewed all columns in a table with \*. You can pick columns by putting in the column name instead of \*. Use SELECT to view the character_id column from the characters table.
61.
