Implementation steps:

1. Provision source - Created or reused an RDS Oracle instance and connected from EC2 using Oracle
Instant Client SQL*Plus. Populated ADMIN.CUSTOMERS with five test records.

2. Prepare target - Confirmed the Aurora PostgreSQL cluster and writer instance were available. Installed
psql on EC2, connected to the postgres database, and created the lowercase admin schema/table.

3. Configure network - Added narrowly scoped database security-group inbound rules to allow access from
the EC2 security group. Confirmed Oracle TCP 1521 and Aurora PostgreSQL TCP 5432 connectivity.

4. Provision replication - Created a provisioned DMS replication instance in the database VPC and selected
a compatible subnet group.

5. Configure endpoints - Created source and target DMS endpoints and successfully tested both
connections.

6. Create full-load task - Configured a task for migrating existing data, with table mappings for Oracle
ADMIN.CUSTOMERS and the PostgreSQL admin.customers destination. The table was already created on
the target.

7. Start and validate - Started the DMS task and confirmed five Oracle records were copied into
PostgreSQL.
