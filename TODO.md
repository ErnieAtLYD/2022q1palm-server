# Lesson To Dos

> This database can be optimized better, but that will be addressed in the future.

This is a continuation of the migration and seeding lectures. It is assuming you've already migrated and seeded data from that lesson.

### Before we start

Everyone repeat after me: "THIS IS JUST A DEMO ONLY. I DO NOT HAVE TO USE DATABASES FOR OUR INSTOCK PROJECT."

- Understand the schema we'll use
- Design the API endpoints we'd like:

  - GET `/api/warehouses`
  - POST `/api/warehouses`

  - GET `/api/warehouses/:warehouse_id`
  - PUT `/api/warehouses/:warehouse_id`
  - DELETE `/api/warehouses/:warehouse_id`

  - GET `/api/warehouses/:warehouse_id/inventories`
  - POST `/api/warehouses/:warehouse_id/inventories`

  - GET `/api/inventories`
  - POST `/api/inventories`

  - GET `/api/inventories/:inventory_id`
  - DELETE `/api/inventories/:inventory_id`

## Folder Structure

```
/db
  /migrations
  /seeds
/controllers -- business logic for handling API endpoints
  warehouses.js
/models  -- simple collections of db queries and utilities for data
  inventory.js
  warehouse.js
/routes -- defines API endpoints and passes requests to corresponding controllers
  inventories.js
  warehouses.js
db.js -- loads the knexfile using settings for the current environment
index.js -- the main Express app
knexfile.js -- defines all database settings for different environments
package.json -- defines scripts for utilities like migrations and seeds
```

## Diving Deeper

- https://medium.com/truepicinc/queryql-easily-add-filtering-sorting-and-pagination-to-your-node-js-rest-api-9222135c93ae
- https://gist.github.com/NigelEarle/70db130cc040cc2868555b29a0278261
- https://medium.com/@jaeger.rob/seed-knex-postgresql-database-with-json-data-3677c6e7c9bc
