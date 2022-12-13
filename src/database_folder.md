# Database Folder

This [`folder`](https://github.com/testnetrunn/explorer-backend/tree/main/src/database) contains files that will hide the complexity of working with MongoDB.

[`database_tr.rs`](https://github.com/testnetrunn/explorer-backend/blob/main/src/database/database_tr.rs) file contains the definition of [`DatabaseTR`](https://github.com/testnetrunn/explorer-backend/blob/main/src/database/database_tr.rs#L10) struct which provides an object to work with databases.

[`DatabaseTR`](https://github.com/testnetrunn/explorer-backend/blob/main/src/database/database_tr.rs#L10) struct must have methods to get/save specific data types implemented, to ease the use.

All the other files represent a specific data type that will be saved to the database.
