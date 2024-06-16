# growtopia
growtopia worlds database


SQLite Database of Growtopia World Names


| name | status    |
|------|-----------|
| world name | indicates the status |
| TEXT | INTEGER |

### Example
| name | status    |
|------|-----------|
| xvqw | 1 |

Means that world is not banned and its already created.


| name | status    |
|------|-----------|
| vaxt | 0 |

Means that world is banned or not yet created.

### Usage

*Javascript(Node.js)* 


In terminal to install the required library:

```bash
npm install better-sqlite3
```

index.js

```js
const Database = require('better-sqlite3')
const db = new Database('./growtopia.sqlite')

const your_name = 'turk' // The world you want to check
cons row = db.prepare('SELECT * FROM growtopia WHERE name = ?').get(your_world_name);

console.log(
// returns { name: 'turk', status: 1 }

```

In terminal to run the file:

```bash
node index.js
```

---

*Python*


In terminal to install the required library:
```bash
pip install sqlite3
```

main.py

```python
import sqlite3

database = sqlite3.connect('./growtopia.sqlite')
cursor = database.cursor()

your_name = 'turk' # The world you want to check

cursor.execute('SELECT * FROM growtopia WHERE name = ?', (your_name))

row = cursor.fetchone()

print(row)
# returns ("turk", 1)

```

In terminal to run the file:


```bash
python main.py
```


