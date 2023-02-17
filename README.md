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

2. Adding new columns to a data set

   ##### Result
   Bump the minor version because we have changed the shape of the data set. Might want to combine this with `BREAKING_CHANGE` to signal an important new column was added. May be useful for surveys, where a new question was added after years of it previously not existing. Participant would now be getting version 2 of the survey.

   ##### Rule
   ```
   {"type": "data", "scope": "add-column", "release": "minor"},
   ```

   ##### Commit message
   ```
   data(add-column): added new columns to the data set
   ```

3. Removing rows from a data set

   ##### Result
   Bump the minor version because, although we have changed the shape of the data set, the number of columns stays the same and it should not impact (as much?) how data is read by a program.

   ##### Rule
   ```
   {"type": "data", "scope": "remove-row", "release": "minor"},
   ```

   ##### Commit message
   ```
   data(remove-row): remove rows from the data set
   ```

4. Removing columns from a data set

   ##### Result
   Bump the major version because we have changed the shape of the data set in a way that could brake the way people previously read the data.

   ##### Rule
   ```
   {"type": "data", "scope": "remove-column", "release": "major"},
   ```

   ##### Commit message
   ```
   data(remove-column): remove columns from the data set
   ```

5. Changing values in a previously published data set

   ##### Result
   Bump the patch version because we have made a change to values in the data set, but have not changed the shape of the data set in a way that could brake the way people previously read the data.

   ##### Rule
   ```
   {"type": "data", "scope": "change-values", "release": "patch"},
   ```

   ##### Commit message
   ```
   data(change-values): changing the value in the data set, but not removing or adding new columns or rows
   ```
