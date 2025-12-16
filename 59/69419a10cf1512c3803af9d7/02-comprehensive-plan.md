### 1. CODEBASE ANALYSIS

Since there are no specific reference files provided, I'll outline a general approach based on typical Node.js and TypeScript projects that use MongoDB. The utility will likely be a standalone module that can be imported and used in various parts of the application. The `mongodb` package will be used to interact with the MongoDB database.

### 2. IMPLEMENTATION STRATEGY

The goal is to create a MongoDB utility that provides simple insert and read operations. This utility will include methods for inserting any JSON schema, finding documents by ID, and finding a single document based on a query. The utility will handle connection errors gracefully and throw an error for duplicate ID insertions.

### 3. COMPREHENSIVE STEP-BY-STEP IMPLEMENTATION PLAN

**Step 1: Create MongoDB Utility File**
- **File**: `src/utils/mongodbUtility.ts`
- **Action**: Create a new file for the MongoDB utility.
- **Details**: 
  - Import necessary modules (`mongodb`, `dotenv` for environment variables).
  - Set up a MongoDB client connection using connection details from environment variables.
  - Export a class `MongoDBUtility` with methods for database operations.
- **Rationale**: This file will encapsulate all MongoDB operations, making it reusable and maintainable.
- **Addresses**: Provides a centralized utility for MongoDB operations.

**Step 2: Implement Connection Handling**
- **File**: `src/utils/mongodbUtility.ts`
- **Action**: Implement connection logic.
- **Details**: 
  - Create a method to connect to the MongoDB database.
  - Handle connection errors and log them.
- **Rationale**: Ensures the utility can connect to the database and handle errors gracefully.
- **Addresses**: Handles MongoDB connection errors without crashing.

**Step 3: Implement Insert Method**
- **File**: `src/utils/mongodbUtility.ts`
- **Action**: Implement a method to insert documents.
- **Details**: 
  - Create an `insertDocument` method that takes a collection name and a JSON object.
  - Use the `insertOne` method from the MongoDB client.
  - Handle duplicate ID errors by checking for error codes and throwing a custom error.
- **Rationale**: Allows insertion of any JSON schema into the database.
- **Addresses**: Inserts valid JSON objects and handles duplicate ID errors.

**Step 4: Implement FindById Method**
- **File**: `src/utils/mongodbUtility.ts`
- **Action**: Implement a method to find documents by ID.
- **Details**: 
  - Create a `findById` method that takes a collection name and an ID.
  - Use the `findOne` method with an ID query.
- **Rationale**: Provides a way to retrieve documents by their unique ID.
- **Addresses**: Retrieves documents by ID.

**Step 5: Implement FindOne Method**
- **File**: `src/utils/mongodbUtility.ts`
- **Action**: Implement a method to find a single document based on a query.
- **Details**: 
  - Create a `findOne` method that takes a collection name and a query object.
  - Use the `findOne` method from the MongoDB client.
- **Rationale**: Allows retrieval of a single document based on a query.
- **Addresses**: Retrieves a single document based on a query.

**Step 6: Add Logging for Operations**
- **File**: `src/utils/mongodbUtility.ts`
- **Action**: Implement logging for database operations.
- **Details**: 
  - Use a logging library or simple console logs to track operations.
  - Log successful operations and errors.
- **Rationale**: Aids in debugging and monitoring database operations.
- **Addresses**: Provides visibility into database operations.

### 4. VALIDATION STRATEGY

- Ensure the utility can insert any valid JSON object into the MongoDB collection.
- Validate that the `findById` method correctly retrieves a document by its ID.
- Ensure the `findOne` method can retrieve a single document based on a query object.
- Check that the utility handles connection errors gracefully.
- Throw an error if a document with the same ID already exists.

### 5. INTEGRATION POINTS

- The utility will be imported and used in other parts of the application where database operations are needed.
- Ensure the utility is compatible with existing database configurations and connection details.

### 6. EDGE CASES & CONSIDERATIONS

- Handle cases where the database connection fails.
- Consider scenarios where the query does not match any documents.
- Ensure proper error handling for all database operations.

### 7. IMPLEMENTATION CONSTRAINTS

- Focus ONLY on core feature implementation.
- DO NOT include unit tests (handled separately).
- Follow existing codebase conventions and patterns.
- Ensure type safety and code quality.
- Maintain backward compatibility where applicable.