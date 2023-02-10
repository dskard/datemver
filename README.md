# datemver
semantic versioning of data

# Custom Commit Messages

## Data Update Scenarios

1. Adding new rows to a data set

   ##### Result
   Bump the minor version because we have changed the shape of the data set.

   ##### Rule
   ```
   {"type": "data", "scope": "add-row", "release": "minor"},
   ```

   ##### Commit message
   ```
   data(add-row): added new rows to the data set
   ```

