## Script: Create db_executor Role and Grant Execute Permissions

**Description**:
This script creates a reusable `db_executor` role within a database and grants it `EXECUTE` permissions. It then adds a user (e.g., an application user) to this role so that the user can execute stored procedures, scalar functions, and other executable objects without having full access to the database.

**Steps Performed**:
1. Creates a role named `db_executor`.
2. Grants `EXECUTE` permission to the role.
3. Adds a user to the role using `ALTER ROLE`.

**Use Case**:
- Assign execution access to application users or developers without giving them full `db_owner` or `db_datareader` access.
- Simplifies permission management in production environments.
- Follows the principle of least privilege.

**Instructions**:
- Replace `application_user` with the actual user name in your database.
- This should be run **inside the target database** where the user exists.

**Requirements**:
- SQL Server 2012 or later
- Requires membership in the `db_owner` role or equivalent to create roles and assign permissions

**Notes**:
- This script does **not** create the user itself — make sure the user already exists in the database.
- You can add multiple users to the same role to manage permissions centrally.
