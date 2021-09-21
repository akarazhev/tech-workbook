# Data migration with the nmig tool

`NMIG` is an app, intended to make a process of migration from `MySQL` to `PostgreSQL` as easy and smooth as possible.
It has been written in the `TypeScript` language and is run on `Node.js 10` or higher.

Visit the link for more information: https://github.com/AnatolyUss/NMIG

## Installation

Download and install `Node.js 10` or higher: https://nodejs.org/en/

Clone and checkout the `nmig` tool:

```bash
git clone https://github.com/AnatolyUss/nmig.git
cd nmig
git checkout v5.5.0
```

## Configuration 

The main configuration script is `config.json`:

```bash
nano config/config.json
```

If we need to configure a source and target, we can update sections:

```json
"source": {
  "host": "localhost",
  "port": 3306,
  "database": "test_db",
  "charset": "utf8mb4",
  "supportBigNumbers": true,
  "user": "root",
  "password": "0123456789"
}
```

```json
"target": {
  "host"     : "localhost",
  "port"     : 5432,
  "database" : "test_db",
  "charset"  : "UTF8",
  "user"     : "postgres",
  "password" : "0123456789"
}
```

If we need to rename either a table name, column or foreign keys, we should activate an extra config:

```json
"enable_extra_config" : false
```

The extra configuration script is `extra_config.json`:

```bash
nano config/extra_config.json
```

To rename names we can update sections:

```json
"tables" : [
  {
    "name": {
      "original": "salary",
      "new": "renamed_salary"
    },
    "columns": [
      {
        "original": "id",
        "new": "renamed_id"
      },
      {
        "original": "employee_id",
        "new": "renamed_employee_id"
      }
    ]
  },
  {
    "name": {
      "original": "contract",
      "new": "renamed_contract"
    },
    "columns": [
      {
        "original": "id",
        "new": "renamed_id"
      }
    ]
  }
]
```

## Usage

Install and run:

```bash
npm install
npm run build
npm start
```

Enjoy!