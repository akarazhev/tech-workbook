# How to Migrate Data with the nmig Tool

`NMIG` is a powerful tool that simplifies the process of migrating from `MySQL` to `PostgreSQL`. 
Built with `TypeScript` for enhanced reliability and maintainability, `NMIG` is a top choice for developers who want 
to streamline their migration process. With `NMIG`, you can enjoy benefits such as:

- Easy and smooth migration from `MySQL` to `PostgreSQL`
- Written in `TypeScript` for improved reliability and maintainability
- Compatible with `Node.js 10` and higher

Visit the official `NMIG` website at https://github.com/AnatolyUss/NMIG to learn more about this versatile tool.

## How to Install NMIG

To install `NMIG`, follow these simple steps:

1. Download and install `Node.js 10` or higher by visiting the official website at https://nodejs.org/en/.
2. Open your command prompt or terminal.
3. Clone the `NMIG` tool by running the following command:
```bash
git clone https://github.com/AnatolyUss/nmig.git
```

4. Navigate to the NMIG directory by running the following command:
```bash
cd nmig
```

5. Check out the version you want to install by running the following command (replace v5.5.0 with the version you want to install):
```bash
git checkout v5.5.0
```

Once you've completed these steps, you're ready to start using NMIG for your data migration needs.

## Configuring the Source and Target 

To configure your source and target databases, follow these steps:

1. Open the `config.json` file by running the following command:
```bash
nano config/config.json
```

2. Update the `source` and `target` sections with your desired configuration, such as host, port, database name, 
character set, username, and password.

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
## Renaming Table Names and Columns

To rename table names and columns, follow these steps:

1. Enable the extra configuration by setting `enable_extra_config` to `true` in the `config.json` file:
```json
"enable_extra_config" : false
```

2. Open the `extra_config.json` file by running the following command:
```bash
nano config/extra_config.json
```

3. Update the `tables` section with the table names and columns you want to rename, using the `original` and `new` keys:

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

With these configurations in place, you're ready to migrate your data using NMIG.

## Usage

Install the required dependencies and build the project by running:
```bash
npm install
npm run build
```

Start the migration process by running:
```bash
npm start
```

Enjoy the migration process!