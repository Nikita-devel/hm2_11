# FastAPI Contacts API

## Overview

This project aims to create a robust REST API for managing contacts using the FastAPI framework and SQLAlchemy for database management. Contacts are stored in a PostgreSQL database and contain essential information, including name, surname, email, phone number, birthday, and optional additional data.

## API Endpoints

### CRUD Operations

1. **Create a New Contact**

   - Endpoint: `POST /contacts/`
   - Request Body:
     ```json
     {
       "name": "John",
       "surname": "Doe",
       "email": "john.doe@example.com",
       "phone_number": "+1234567890",
       "birthday": "1990-01-01",
       "additional_data": "Additional information"
     }
     ```
   - Response:
     ```json
     {
       "id": 1,
       "name": "John",
       "surname": "Doe",
       "email": "john.doe@example.com",
       "phone_number": "+1234567890",
       "birthday": "1990-01-01",
       "additional_data": "Additional information"
     }
     ```

2. **Get List of All Contacts**

   - Endpoint: `GET /contacts/`
   - Response:
     ```json
     [
       {
         "id": 1,
         "name": "John",
         "surname": "Doe",
         "email": "john.doe@example.com",
         "phone_number": "+1234567890",
         "birthday": "1990-01-01",
         "additional_data": "Additional information"
       },
       // ... other contacts
     ]
     ```

3. **Get a Contact by ID**

   - Endpoint: `GET /contacts/{contact_id}/`
   - Response:
     ```json
     {
       "id": 1,
       "name": "John",
       "surname": "Doe",
       "email": "john.doe@example.com",
       "phone_number": "+1234567890",
       "birthday": "1990-01-01",
       "additional_data": "Additional information"
     }
     ```

4. **Update an Existing Contact**

   - Endpoint: `PUT /contacts/{contact_id}/`
   - Request Body:
     ```json
     {
       "name": "Updated John",
       "surname": "Updated Doe",
       // ... other updated fields
     }
     ```
   - Response:
     ```json
     {
       "id": 1,
       "name": "Updated John",
       "surname": "Updated Doe",
       // ... other updated fields
     }
     ```

5. **Delete a Contact**

   - Endpoint: `DELETE /contacts/{contact_id}/`
   - Response:
     ```json
     {
       "message": "Contact successfully deleted"
     }
     ```

### Additional Features

1. **Search Contacts by Name, Surname, or Email**

   - Endpoint: `GET /contacts/search/?query={search_query}`
   - Example: `GET /contacts/search/?query=John`
   - Response:
     ```json
     [
       {
         "id": 1,
         "name": "John",
         "surname": "Doe",
         "email": "john.doe@example.com",
         "phone_number": "+1234567890",
         "birthday": "1990-01-01",
         "additional_data": "Additional information"
       },
       // ... other contacts matching the search query
     ]
     ```

2. **Get Contacts with Birthdays in the Next 7 Days**

   - Endpoint: `GET /contacts/birthdays/`
   - Response:
     ```json
     [
       {
         "id": 1,
         "name": "John",
         "surname": "Doe",
         "email": "john.doe@example.com",
         "phone_number": "+1234567890",
         "birthday": "1990-01-01",
         "additional_data": "Additional information"
       },
       // ... other contacts with birthdays in the next 7 days
     ]
     ```

## Data Validation

All data is validated using Pydantic models, ensuring the accuracy and reliability of the information provided in requests.

## Documentation

API documentation is available at `http://localhost:8000/docs` or `http://localhost:8000/redoc` for easy exploration and understanding of the available endpoints.

## Conclusion

The FastAPI Contacts API provides a comprehensive solution for managing contacts, supporting CRUD operations, search functionalities, and upcoming birthdays retrieval. With its well-documented API and robust data validation, this project offers a reliable and efficient way to handle contact information.
