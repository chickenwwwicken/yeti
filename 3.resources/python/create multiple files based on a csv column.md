
``` python
import pandas as pd

# Read the CSV file
df = pd.read_csv('your_file.csv')

for index, row in df.iterrows():
    # Assuming 'Column_Name' is the column you want to use for naming
    file_name = f"{row['Column_Name']}.csv"
    
    # Create a new DataFrame with just this row's data
    new_df = pd.DataFrame([row])
    
    # Save the new DataFrame to a CSV file with the dynamic name
    new_df.to_csv(file_name, index=False)

```
## groupby() for multiple columns


``` python
import pandas as pd

# Read the CSV file
df = pd.read_csv('your_file.csv')

# Group by multiple columns
for (col1_value, col2_value), group in df.groupby(['Column1', 'Column2']):
    file_name = f"{col1_value}_{col2_value}.csv"
    group.to_csv(file_name, index=False)
```

## Dynamic Naming with Date and time
``` python
from datetime import datetime

for index, row in df.iterrows():
    # Get current date and time
    now = datetime.now().strftime("%Y%m%d_%H%M%S")
    file_name = f"{row['Column_Name']}_{now}.csv"
    
    new_df = pd.DataFrame([row])
    new_df.to_csv(file_name, index=False)
```

## Using a Cuustom Function

``` python
def generate_file_name(row):
    # Custom logic to generate file name
    return f"{row['Column1']}_{row['Column2']}.csv"

for index, row in df.iterrows():
    file_name = generate_file_name(row)
    new_df = pd.DataFrame([row])
    new_df.to_csv(file_name, index=False)

```