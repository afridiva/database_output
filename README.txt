Query 1

The following create query creates a new table users with 9 fields. 
The id field is its primary key while the role_id is a foreign key that points to the roles table. This table can only be created after roles table has been created so that it does not reference an undefined field.
------------------------------------------------------------------------------------
CREATE TABLE cars(
	id INT AUTO_INCREMENT PRIMARY KEY,
	first_name VARCHAR(30) NOT NULL,
	last_name VARCHAR(30) NOT NULL,
	email VARCHAR(50),
	password VARCHAR(30),
	address VARCHAR(100),
	phone_number INT(11),
	role_id INT(2),
	last_login TIMESTAMP,
	FOREIGN KEY fk_role(role_id) REFERENCES roles(id) ON DELETE CASCADE
);

====================================================================================

Query 2

The following query selects all users who are students ie whose ids exist on students table
------------------------------------------------------------------------------------
SELECT * from users where id in (select id from students);

====================================================================================

Query 3

The following query inserts a new role into the roles table. id is ignored since it is the primary key so it auto increments
------------------------------------------------------------------------------------
INSERT INTO roles (name) VALUES('admin');
====================================================================================

Query 4

The following deletes 'ALL' entries of the tests table.
------------------------------------------------------------------------------------
DELETE FROM tests
====================================================================================

Query 5
------------------------------------------------------------------------------------