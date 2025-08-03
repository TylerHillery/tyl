# Tyl  
**A modern language for data that aims to be a superset of SQL**  
*(pronounced like "tile")*

> ⚠️ **Note: This project is experimental and not under active development.**  
> Tyl is currently a collection of early ideas and design explorations. It is not production-ready, and the language, tooling, and features described here are subject to significant change or may never be fully implemented.

---

## Overview

SQL was built on a standard but in practice, every engine speaks its own dialect. **Tyl** unifies these variations by compiling to multiple targets (Postgres, DuckDB, Snowflake, etc.) from a single, clean, typed source.


###  Key Design Goals

- **Cross-dialect Compilation** — Compile a single Tyl source into many SQL dialects
- **Typed Schema & Migrations** — Built-in modeling, versioning, and validation
- **Modern Tooling Support** — LSP, formatter, linter, test runner, and package manager
- **Column-level Lineage** — Understand how every field is derived
- **Composable & Reusable** — Importable modules and type-safe client code generation

---

## Project Components

- [ ] **Compiler**  
    - Input: `.tyl` files  
    - Output: SQL for target dialects
- [ ] **Type Checker**  
    - Structural + semantic validation of schema and queries  
- [ ] **Linter**  
    - Best practices, unused models, redundant joins  
- [ ] **Formatter**  
    - Canonical code style (like `prettier`)  
- [ ] **LSP**  
    - Editor support (VSCode, Neovim, etc.)  
- [ ] **Test Framework**  
    - Declarative data tests and query output assertions  
- [ ] **Package Manager**  
    - Modules, versioning, deps, publishing  
- [ ] **Schema Migration**  
    - Auto + manual migration scripts  
- [ ] **Column-Level Lineage**  
    - Understand how columns are derived/transformed  
- [ ] **Client Libraries**  
    - Raw SQL (e.g., Yesql, aiosql-style)  
    - Query Builder  
    - ORM-ish interfaces

---

## Languages to Evaluate for Compiler

- **Rust**
- **Zig**
- **Mojo**

---

## Resources

### Papers 
- [A Relational Model of Data for Large Shared Data Banks](https://dl.acm.org/doi/10.1145/362384.362685)
- [Further Normalization of the Data Base Relational Model](https://forum.thethirdmanifesto.com/wp-content/uploads/asgarosforum/987737/00-efc-further-normalization.pdf)
- [What Goes Around Comes Around... and Around...](https://db.cs.cmu.edu/papers/2024/whatgoesaround-sigmodrec2024.pdf)
- [Apache Calcite: A Foundational Framework for Optimized Query Processing Over Heterogeneous Data Sources](https://arxiv.org/pdf/1802.10233)
- [A Critique of Modern SQL And A Proposal Towards A Simple and Expressive Query Language](https://www.cidrdb.org/cidr2024/papers/p48-neumann.pdf)

### Videos
- [CMU DB Group - SQL or Death](https://www.youtube.com/playlist?list=PLSE8ODhjZXjbpOIrZheFWxkYG8HD87xW1)

### Docs
- [The SQL Standard](https://blog.ansi.org/ansi/sql-standard-iso-iec-9075-2023-ansi-x3-135/)

---

## Inspiration

- [Convex](https://convex.dev)
- [Malloy](https://github.com/malloydata/malloy)
- [PRQL](https://prql-lang.org)
- [Ibis](https://ibis-project.org)
- [Fugue](https://github.com/fugue-project/fugue)
- [Morel](https://github.com/hydromatic/morel)
- [SQLGlot](https://github.com/tobymao/sqlglot)
- [Substrait](https://substrait.io)
- [Dbt + SDF fusion](https://www.getdbt.com)
- [ANTLR](https://www.antlr.org)
- [Apache Calcite](https://calcite.apache.org)
- [Prisma](https://www.prisma.io)
- [Drizzle](https://orm.drizzle.team)
- [GelDB](https://github.com/geldata/gel)
- [Datafusion](https://github.com/apache/datafusion)

---

## Related Ecosystem Tools

### Raw SQL Libraries

#### JavaScript / TypeScript
- [PgTyped](https://github.com/adelsz/pgtyped) – Type-safe SQL in TypeScript for Postgres
- [Prisma](https://www.prisma.io/docs/orm/prisma-client/using-raw-sql/typedsql) – Also supports raw SQL with type inference

#### Go
- [sqlc](https://github.com/sqlc-dev/sqlc) – Generate type-safe code from SQL
- [pgx](https://github.com/jackc/pgx) – PostgreSQL driver and toolkit for Go

#### Rust
- [sqlx](https://github.com/launchbadge/sqlx) – The Rust SQL Toolkit 

#### Python
- [aiosql](https://nackjicholson.github.io/aiosql/) - Simple SQL in Python 
- [records](https://github.com/kennethreitz/records) – SQL for Humans 
- [PugSQL](https://pugsql.org) – a simple Python interface for using parameterized SQL, in files, with SQL-in-files with function mapping

#### Clojure
- [Yesql](https://github.com/krisajenkins/yesql) – A Clojure library for using SQL

#### Gleam
- [Squirrel](https://github.com/lpil/squirrel) – Type safe SQL in Gleam 


### Query Builders

#### JavaScript / TypeScript
- [Knex](https://knexjs.org) – Batteries included" SQL query builder
- [Kysely](https://kysely.dev) – The type-safe SQL query builder for TypeScript

#### Go
- [sqlbuilder](https://github.com/huandu/go-sqlbuilder) – A flexible and powerful SQL string builder library plus a zero-config ORM
- [goqu](https://github.com/doug-martin/goqu) – SQL builder and query library for golang

#### Java
- [JOOQ](https://www.jooq.org) – Type-safe SQL for Java


### ORMs

#### JavaScript / TypeScript
- [Drizzle](https://orm.drizzle.team) – ORM for you to ship ship ship
- [Prisma](https://www.prisma.io) – Next-generation ORM for Node.js & TypeScript
- [Sequelize](https://sequelize.org) – Modern TypeScript and Node.js ORM

#### Python
- [SQLAlchemy](https://www.sqlalchemy.org) – Python SQL Toolkit and ORM 
- [SQLModel](https://sqlmodel.tiangolo.com) – Pydantic + SQLAlchemy
- [Django ORM](https://docs.djangoproject.com/en/stable/topics/db/models/) – Built-in ORM for Django

#### Go
- [ent](https://entgo.io) – Simple, yet powerful ORM for modeling and querying data
- [GORM](https://gorm.io) – The fantastic ORM library for Golang

#### Rust
- [Diesel](https://diesel.rs) – Diesel is a Safe, Extensible ORM and Query Builder for Rust

#### Ruby
- [Active Record](https://guides.rubyonrails.org/active_record_basics.html) – Rails' built-in ORM

#### Elixir
- [Ecto](https://hexdocs.pm/ecto/Ecto.html) – A toolkit for data mapping and language integrated query

#### Java
- [Hibernate](https://hibernate.org) – Industry-standard ORM with JPA

#### Kotlin
- [Exposed](https://github.com/JetBrains/Exposed) – Kotlin SQL Framework 

#### Scala
- [Quill](https://getquill.io) – Compile-time Language Integrated Queries for Scala

#### PHP
- [Eloquent](https://laravel.com/docs/eloquent) – Laravel's elegant ORM
- [Doctrine](https://www.doctrine-project.org) – Data mapper + ORM

#### C#
- [Entity Framework](https://learn.microsoft.com/en-us/ef/) – Microsoft’s official ORM for .NET