# Step-by-Step Guide: MongoDB Library Management System

This guide provides detailed instructions for using the Library Management System with MongoDB Compass.

## Initial Setup

### 1. Database Creation and Data Import
1. Open terminal/command prompt
2. Run MongoDB service
3. Execute the setup script:
   ```bash
   mongosh --file index.js
   ```
   This creates the database with sample books, authors, and patrons.

### 2. MongoDB Compass Setup
1. Download MongoDB Compass
2. Launch the application
3. Connect using: `mongodb://localhost/LibraryDB`

## Basic Operations Guide

### Viewing Collections
1. Click on `LibraryDB` in the left sidebar
2. You'll see three collections:
   - `books`
   - `authors`
   - `patrons`

### Query Examples

#### 1. Finding Books
```json
// Find all available books
{ "available": true }

// Find books by title
{ "title": "To Kill a Mockingbird" }

// Find books by author ID
{ "author_id": 5 }
```

#### 2. Finding Authors
```json
// Find American authors
{ "nationality": "American" }

// Find authors by name pattern
{ "name": { "$regex": /George/ } }
```

#### 3. Finding Patrons
```json
// Find patrons with borrowed books
{ "borrowed_books": { "$ne": [] } }
```

## Advanced Operations

### 1. Updating Records

#### Update Book Availability
1. Select the `books` collection
2. Click "Add Filter"
3. Enter: `{ "_id": 3 }`
4. Click "Update"
5. Enter update operation:
   ```json
   { "$set": { "available": false } }
   ```

#### Add Genre to Book
1. Select book with `_id: 8`
2. Use update operation:
   ```json
   { "$addToSet": { "genres": "Novel" } }
   ```

### 2. Data Analysis

#### Using Aggregation Pipeline
1. Click "Aggregations" tab
2. Example: Count books by genre
   ```json
   [
     { "$unwind": "$genres" },
     { "$group": { "_id": "$genres", "count": { "$sum": 1 } } }
   ]
   ```

### 3. Data Visualization

#### Create Charts
1. Click "Charts" tab
2. "New Chart"
3. Example visualizations:
   - Books by publication year
   - Authors by nationality
   - Patron borrowing patterns

## Common Tasks

### 1. Adding New Book
1. Select `books` collection
2. Click "Add Data"
3. Template:
   ```json
   {
     "_id": 11,
     "title": "New Book Title",
     "author_id": 1,
     "genres": ["Genre1", "Genre2"],
     "published_year": 2024,
     "available": true
   }
   ```

### 2. Managing Loans
1. Update book availability
2. Update patron's borrowed_books
3. Example workflow:
   ```json
   // Mark book as unavailable
   db.books.updateOne(
     { "_id": bookId },
     { "$set": { "available": false } }
   )
   
   // Add to patron's borrowed books
   db.patrons.updateOne(
     { "_id": patronId },
     { "$addToSet": { "borrowed_books": bookId } }
   )
   ```

## Troubleshooting

### Common Issues and Solutions

1. Connection Failed
   - Check MongoDB service is running
   - Verify connection string
   - Check port availability (default: 27017)

2. Query Not Returning Results
   - Check field names (case sensitive)
   - Verify data types match
   - Use MongoDB Compass's query builder

3. Update Operations Failed
   - Check document exists
   - Verify correct operator usage
   - Check for duplicate key errors

## Best Practices

1. Always use filters before updates
2. Back up data before bulk operations
3. Use appropriate indexes for frequent queries
4. Monitor query performance
5. Use meaningful document IDs

## Additional Resources

- [MongoDB Documentation](https://docs.mongodb.com/)
- [MongoDB Compass Guide](https://docs.mongodb.com/compass/current/)
- [MongoDB Query Operators](https://docs.mongodb.com/manual/reference/operator/query/) 