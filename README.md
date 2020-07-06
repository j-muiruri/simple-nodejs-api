# simple-nodejs-api
This is a simple api that performs basic crud operations on employee data
# Requirements
  - Nodejs
  - MySQL
# Steps
1. Create your database and  add the following code to create an "employee" table.
      ```mysql
      CREATE  TABLE IF NOT EXISTS `employees` (
        `id` BIGINT UNSIGNED AUTO_INCREMENT,
        `first_name` VARCHAR(255) NOT NULL,
        `last_name` VARCHAR(255) NOT NULL,
        `email` VARCHAR(255) NOT NULL,
        `phone` VARCHAR(50) NOT NULL,
        `organization` VARCHAR(255) NOT NULL,
        `designation` VARCHAR(100) NOT NULL,
        `salary` DECIMAL(11,2) UNSIGNED DEFAULT 0.00,
        `status` TINYINT UNSIGNED DEFAULT 0,
        `is_deleted` TINYINT UNSIGNED DEFAULT 0,
        `created_at` DATETIME NOT NULL,
        `updated_at` DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
        PRIMARY KEY (`id`))
      ENGINE = InnoDB;
      ```

2. Edit the ```db.config.js``` file in the folder ```/src``` and add your database name, username and password
4. run ```npm update ``` on your commandline: ```bash/cmd```
```bash 
npm update
```
5. Now deploy your app by running ```npm start```, ```start``` command is defined in the ```package.json``` file and runs the ```nodemon server``` command
```bash 
npm start
```
6. The application can be accessed on this url [http://localhost:5000](http://localhost:5000)
# API End Points
List all employees stored in database
```http
    GET /api/v1/employees: 
```
Get a specific employee with employee_id
```http
    GET /api/v1/employees/<employee_id>: 
```
Create  employee
```http
    POST /api/v1/employees : 
```
Update employee partially
```http
    PATCH /api/v1/employees/<employee_id>
``` 
Delete a employee
```http
    DELETE /api/v1/employees/<employee_id>
```
 Update employee completely
```http
    PUT /api/v1/employees/<employee_id>
```
