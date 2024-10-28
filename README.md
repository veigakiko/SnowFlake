# Connect to Snowflake


```sh
!pip install snowflake-connector-python

```


```sh
import snowflake.connector

# Connect to Snowflake
conn = snowflake.connector.connect(
    user='xxxxxx',
    password='xxxxx',  # Ensure password is handled securely
    account='jb25481.us-east4.gcp',  # Corrected account for GCP US East 4
    warehouse='COMPUTE_WH',
    database='DB_IBJJF',
    schema='IBJJF',
    role='ACCOUNTADMIN'
)

# Test the connection by executing a simple query
try:
    conn.cursor().execute("SELECT 1")
    print("Successfully connected to Snowflake!")
except Exception as e:
    print(f"Connection error: {e}")
```


```sh
conn.cursor().execute("SELECT CURRENT_DATABASE(), CURRENT_SCHEMA()").fetchall()
```
