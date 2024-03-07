# Learn Relational Databases by Building a Mario Database

1. Your virtual machine comes with PostgreSQL installed. You will use the Psql terminal application to interact with it. Log in by typing `psql --username=freecodecamp --dbname=postgres` into the terminal and pressing enter.
2. Notice that the prompt changed to let you know that you are now interacting with PostgreSQL. First thing to do is see what databases are here. Type \l into the prompt to list them.
3. The databases you see are there by default. You can make your own like this:
   `CREATE DATABASE database_name;`
   The capitalized words are keywords telling PostgreSQL what to do. The name of the database is the lowercase word. **Note that all commands need a semi-colon at the end**. Create a new database named **first_database**.
4. It worked. Your new database is there. If you don't get a message after entering a command, it means it's incomplete and you likely forgot the **semi-colon**. You can just add it on the next line and press enter to finish the command. Create another database named **second_database**
5. You can connect to a database by entering `\c database_name`. You need to connect to add information. Connect to your second_database.
6. You should see a message that you are connected. Notice that the prompt changed to **second_database=>**. So the **postgres=>** prompt before must have meant you were connected to that database. A database is made of tables that hold your data. Enter `\d` to **display** the tables.
