# spl
# pythonSQL

## Project Overview
pythonSQL is a project developed using Python. Its core functionality is to simulate some of the features of a MySQL database using SQLite. This project includes operations for data insertion, deletion, update, and query, as well as the creation and deletion of database tables. It provides developers with a lightweight and convenient database operation solution.

## Installation Steps
### Environment Requirements
- Operating System: Windows 10 (Test Environment)
- Python Version: The latest version

### Dependency Installation
This project depends on the `Flask` library. You can install it using the following command:
```bash
pip install flask
```

## Usage Instructions
### Configure Database Connection
You can configure the database connection information in a configuration file and also set it directly in the code. Here is a simple example:
```python
import sqlite3
from flask import Flask

app = Flask(__name__)

# Configure the SQLite database connection
conn = sqlite3.connect('your_database.db')
cursor = conn.cursor()

# Other code...

if __name__ == '__main__':
    app.run(debug=True)
```

### Start the Project
After completing the configuration, you can start the project using the following command:
```bash
python your_main_file.py
```

### Database Operation Examples
#### Create a Table
```python
cursor.execute('''CREATE TABLE IF NOT EXISTS users
                  (id INTEGER PRIMARY KEY AUTOINCREMENT, name TEXT, age INTEGER)''')
```

#### Insert Data
```python
cursor.execute("INSERT INTO users (name, age) VALUES ('John', 25)")
conn.commit()
```

#### Query Data
```python
cursor.execute("SELECT * FROM users")
rows = cursor.fetchall()
for row in rows:
    print(row)
```

#### Update Data
```python
cursor.execute("UPDATE users SET age = 26 WHERE name = 'John'")
conn.commit()
```

#### Delete Data
```python
cursor.execute("DELETE FROM users WHERE name = 'John'")
conn.commit()
```

#### Delete a Table
```python
cursor.execute("DROP TABLE IF EXISTS users")
```

## Contribution Guidelines
Currently, there are no specific contribution processes or code style requirements for this project. However, we still encourage everyone to follow the PEP 8 code style guide. If you are interested in contributing code, feel free to submit a Pull Request.

## License
This project has not yet determined a license.

## Contact Information
- Email: ziy3207222-@outlook.com
- Website: bilibili-wrbq.cn
