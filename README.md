# UnicornFarm - Bruno API Testing Collection

A comprehensive Bruno collection for automated testing of CRUD operations on a unicorn API, featuring robust validation and test automation workflows.

## Overview

This Bruno collection automates **Create, Read, Update, and Delete (CRUD)** operations for a unicorn API, ensuring data integrity and API functionality through comprehensive testing scenarios.

## Features

- ✅ **Complete CRUD Operations** - Create, read, update, and delete unicorn resources
- ✅ **Schema Validation** - JSON schema validation using Ajv for response structure verification
- ✅ **Status Code Assertions** - Comprehensive HTTP status code checking
- ✅ **Variable Management** - Dynamic data handling with environment and runtime variables
- ✅ **Automated Cleanup** - Clean state management between test runs
- ✅ **Sequential Testing** - Ordered test execution with data persistence across requests

## Test Workflow

1. **Create Unicorn** - Adds a new unicorn resource with test data
2. **Verify Creation** - Validates the created unicorn with status code (200) and schema validation
3. **Update Unicorn** - Modifies existing unicorn data using the captured ID
4. **Verify Update** - Confirms successful data modification
5. **Delete Unicorn** - Removes the unicorn resource
6. **Verify Deletion** - Ensures unicorn no longer exists (404 status expected)

## Environment Setup

The collection uses environment variables for flexibility:

- `BaseURL` - API endpoint base URL (configured in `environments/Test.bru`)

## Runtime Variables

The tests utilize runtime variables for data persistence:

- `unicornId` - Stores the ID of created unicorn for subsequent operations
- `fullApiPostResponse` - Captures complete response for validation
- `updatedUnicornData` - Tracks updated data for verification

## Prerequisites

Before running this test collection, ensure you have:

- **Bruno API Client** - Download and install from [Bruno's official website](https://www.usebruno.com/)
- **Active Internet Connection** - Required to access the CrudCrud API endpoint
- **Valid API Endpoint** - The CrudCrud endpoint in the environment may expire; update `BaseURL` in `environments/Test.bru` if needed

## Getting Started

### Import Collection
1. **Clone Repository** - Clone this repository to your local machine
2. **Open Bruno** - Launch the Bruno API client
3. **Import Collection** - Use "Open Collection" and navigate to the UnicornFarm folder
4. **Select Environment** - Choose the "Test" environment from the environment dropdown

### Verify Environment Setup
1. Navigate to `environments/Test.bru`
2. Ensure the `BaseURL` is valid and accessible
3. Test the base URL in your browser or with a simple GET request

## How to Execute Tests

### Option 1: Run Individual Requests
1. **Manual Execution** - Click on each request in sequence:
   - Create a new unicorn
   - Get the new unicorn
   - Update the new unicorn
   - Get the updated unicorn
   - Delete the unicorn
   - Get the deleted unicorn

### Option 2: Run Entire Collection
1. **Collection Runner** - Use Bruno's collection runner feature
2. **Right-click** on the collection name
3. **Select "Run Collection"** to execute all requests in sequence
4. **Monitor Results** - View test results and assertions in the runner interface

### Option 3: Command Line Execution (if Bruno CLI is available)
```bash
# Navigate to collection directory
cd path/to/UnicornFarm

# Run the entire collection
bruno run --env Test
```

## Expected Test Results

- ✅ **Create Unicorn**: Status 201 (Created)
- ✅ **Get New Unicorn**: Status 200 (OK) with schema validation
- ✅ **Update Unicorn**: Status 200 (OK) 
- ✅ **Get Updated Unicorn**: Status 200 (OK) with updated data verification
- ✅ **Delete Unicorn**: Status 200 (OK)
- ✅ **Get Deleted Unicorn**: Status 404 (Not Found)

## Test Data Structure

```json
{
  "name": "Alfa Test",
  "age": 21,
  "colour": "grey"
}
```

## Validation Features

- **Status Code Verification** - Ensures proper HTTP responses
- **JSON Schema Validation** - Validates response structure and data types
- **Deep Equality Checks** - Verifies response content accuracy
- **Error Handling** - Proper validation of error scenarios (404 for deleted resources)

## Files Structure

```
UnicornFarm/
├── bruno.json                    # Collection configuration
├── collection.bru               # Collection documentation
├── Create a new unicorn.bru     # POST request to create unicorn
├── Get the new unicorn.bru      # GET request to verify creation
├── Update the new unicorn.bru   # PUT request to update unicorn
├── Get the updated unicorn.bru  # GET request to verify update
├── Delete the unicorn.bru       # DELETE request to remove unicorn
├── Get the deleted unicorn.bru  # GET request to verify deletion
└── environments/
    └── Test.bru                 # Environment variables
```

## API Endpoint

This collection is configured to test against the CrudCrud API service for demonstration purposes.

---

**Note**: This is an automated testing suite designed to validate API functionality and data integrity through comprehensive CRUD operations testing.
