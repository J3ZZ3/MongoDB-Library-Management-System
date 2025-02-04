# MongoDB Library Management System

A simple library management system built with MongoDB that demonstrates CRUD operations and advanced queries.

## Prerequisites

- MongoDB Server (version 4.4 or higher)
- MongoDB Compass (GUI tool)
- Node.js (version 12 or higher)

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/J3ZZ3/MongoDB-Library-Management-System.git
   cd MongoDB-Library-Management-System
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start MongoDB service on your system:
   - Windows: `net start MongoDB`
   - macOS: `brew services start mongodb-community`
   - Linux: `sudo systemctl start mongod`

## Database Setup

1. Using MongoDB Shell (mongosh):
   ```bash
   mongosh --file index.js
   ```
   This will create the database and populate it with sample data.

## Using MongoDB Compass

### Initial Setup

1. Download MongoDB Compass from [MongoDB's official website](https://www.mongodb.com/try/download/compass)
2. Install and launch MongoDB Compass
3. Connect to your database:
   - Connection string: `mongodb://localhost/LibraryDB`
   - Click "Connect"

### Working with Collections

The database contains three collections:
- `books`: Store book information
- `authors`: Store author details
- `patrons`: Store library member information

### Common Operations

#### Viewing Data
1. Select the `LibraryDB` database
2. Click on any collection to view its documents
3. Use the filter bar for custom queries

#### Creating Documents
1. Click "Add Data" → "Insert Document"
2. Enter document data in JSON format:
   ```json
   {
     "title": "New Book",
     "author_id": 1,
     "genres": ["Fiction"],
     "published_year": 2024,
     "available": true
   }
   ```

#### Sample Queries

1. Find all available books:
   ```json
   { "available": true }
   ```

2. Find books by specific author:
   ```json
   { "author_id": 5 }
   ```

3. Find books published after 1950:
   ```json
   { "published_year": { "$gt": 1950 } }
   ```

4. Find American authors:
   ```json
   { "nationality": "American" }
   ```

### Data Visualization

MongoDB Compass provides various visualization tools:
1. Click on the "Charts" tab
2. Create new charts using the "New Chart" button
3. Select fields to visualize
4. Choose chart types (bar, line, pie, etc.)

## Project Structure

```
├── index.js          # Main database operations file
├── package.json      # Project configuration
└── README.md         # Documentation
```

## Available Operations

### Read Operations
- Find all books
- Find specific book by title
- Find books by author
- Find available books

### Update Operations
- Update book availability
- Add new genres to books
- Update patron's borrowed books

### Delete Operations
- Delete books
- Delete authors

### Advanced Queries
- Find books by publication date
- Find authors by nationality
- Update multiple documents
- Use regex for pattern matching

## Troubleshooting

1. Connection Issues:
   - Verify MongoDB service is running
   - Check connection string
   - Ensure correct port (default: 27017)

2. Query Issues:
   - Verify correct collection names
   - Check field names and data types
   - Use MongoDB Compass's query builder for help


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



