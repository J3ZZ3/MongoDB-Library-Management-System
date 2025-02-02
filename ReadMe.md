This project will perform the following CRUD Operations

READ
Find All Books
Find a Specific Book by Title (title: "To Kill a Mockingbird")
Find All Books by a Specific Author (author_id: 5)
Find All Available Books

UPDATE
Update Book Availability (Using $set), mark a book (_id: 3 as borrowed.
Add a Genre to a Book (Using $addToSet) (_id: 8)
Add a borrowed book to a patron's record (_id: 5)

DELETE
Delete a Book by Title (title: "Brave New World")
Delete an Author (_id: 3)

Advanced Queries with Operators
Find Books Published After 1950 (Using $gt)
Find All American Authors (Using $eq)
Set All Books To Available (Using $set)
Find All Books That Are Available And Published After 1950
Find authors whose names contain "George" (Using $regex)
Increment the published year of "1869" by 1 (Using $inc)

## How to Run

1. To run this you need to have MongoDB and mongosh installed.
2. Run the following command in your terminal:
   ```bash
   ~ mongosh --file index.js
   ```

## Using MongoDB Compass

1. **Install MongoDB Compass**: Download and install MongoDB Compass from the [official website](https://www.mongodb.com/try/download/compass).

2. **Connect to Your Database**:
   - Open MongoDB Compass.
   - In the "New Connection" window, enter the connection string: `mongodb://localhost/LibraryDB`.
   - Click on "Connect".

3. **Explore Collections**:
   - Once connected, you will see the `LibraryDB` database.
   - Click on the `books`, `authors`, and `patrons` collections to view the documents.

4. **Perform CRUD Operations**:
   - **Create**: Use the "Insert Document" button to add new entries.
   - **Read**: Click on a collection to view all documents. You can also use the filter bar to search for specific documents.
   - **Update**: Select a document and click on "Edit Document" to modify its fields.
   - **Delete**: Select a document and click on "Delete Document" to remove it.

5. **Run Queries**:
   - Use the "Filter" option to run queries similar to those in the `index.js` file. For example, to find all available books, you can use:
     ```json
     { "available": true }
     ```

6. **Visualize Data**: MongoDB Compass provides various visualization tools to help you understand your data better.



