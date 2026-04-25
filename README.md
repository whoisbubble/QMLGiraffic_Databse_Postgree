# GIRAFFIC Database

PostgreSQL database for the **GIRAFFIC** project.

This repository contains a full database dump with schema, roles, permissions, functions, procedures, views, triggers, and demo data required to run the application.

## Overview

The database is designed for managing events, staff assignments, clients, and scheduling.
Most of the business logic is implemented directly inside the database using PL/pgSQL.

## Features

* Relational schema with constraints and indexes
* Role-based access system (`giraffic_admin`, `giraffic_manager`, `giraffic_guest`)
* Stored procedures for core operations
* Triggers for validation and auditing
* DML and DDL audit system
* Views for simplified data access
* Demo data for testing

## Requirements

* PostgreSQL 14 or higher

## Quick Start

### 1. Create database

```bash
createdb giraffic_db
```

### 2. Restore roles (if using globals.sql)

```bash
psql -U postgres -f globals.sql
```

### 3. Restore database

If using dump file:

```bash
pg_restore -U postgres -d giraffic_db giraffic.dump
```

If using SQL file:

```bash
psql -U postgres -d giraffic_db -f giraffic.sql
```

## Roles

The database includes predefined roles:

* `giraffic_admin` — full access
* `giraffic_manager` — operational access
* `giraffic_guest` — limited access

These roles are used by the application for access control.

## Default Credentials

This repository includes default credentials intended for development and testing.

> ⚠️ Do not use these credentials in production environments.

## Structure (logical)

```text
schema          tables, constraints, indexes
functions       PL/pgSQL functions
procedures      stored procedures
views           database views
roles           roles and permissions
audit           audit triggers and logs
```

## Notes

* The database contains both DML and DDL audit mechanisms.
* Business logic is intentionally implemented at the database level.
* Designed for educational and demonstration purposes.

## Related Project

Main application repository:

👉 [https://github.com/whoisbubble/qmlgiraffic](https://github.com/whoisbubble/QMLGiraffic)

## License

Specify your license here (e.g., MIT)
