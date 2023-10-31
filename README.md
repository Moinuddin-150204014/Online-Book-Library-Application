# Online Book Library Application

This project is an Online Book Library application designed to provide users with a platform for managing their book-related activities. It serves as a back-end only application, focusing on the development of RESTful API endpoints. The application is built using Java Spring Boot and utilizes Spring Security for role-based authentication. MySQL is used as the backend database to store user and book-related information.

## Key Features

### User Management Endpoints
1. **/user/register:** This endpoint allows users to register by providing their personal information, including first name, last name, email, password, and address.
2. **/user/login:** Users can log in using their email and password, receiving a token as a response for authentication. User email should be present in the payload data.
3. **/users/{userId}:** Retrieve user details by userId. Only users with ADMIN roles should have access to this API.
4. **/users/{userId}/books:** Retrieve the books borrowed or owned by a specific user. This endpoint can be accessed by the user to view their own books or by an ADMIN to view any user's books.
5. **/users/{userId}/borrowed-books:** Retrieve the books currently borrowed by a specific user. This endpoint can be accessed by the user to view their own borrowed books or by an ADMIN to view any user's borrowed books.

### Books Management
1. **/books/create:** This endpoint is used to add a new book to the database. Users must have the "ADMIN" role to use this API.
2. **/books/update:** Update a book's data that is already saved in the database. Users must have the "ADMIN" role to use this API.
3. **/books/delete:** Delete a book from the database. Users must have the "ADMIN" role to use this API.
4. **/books/all:** Fetch and display all the books data stored in the database. Users must have either the "ADMIN" or "CUSTOMER" role to use this API.

### Book Borrowing/Returning Endpoints
1. **/books/{bookId}/borrow:** Allow users (CUSTOMER) to borrow a book by bookId. Implement logic to track the book's availability and due date.
2. **/books/{bookId}/return:** Allow users (CUSTOMER) to return a borrowed book by bookId. Update the book's status accordingly.

### Book Reservation Endpoints (Optional)
1. **/books/{bookId}/reserve:** Allow users (CUSTOMER) to reserve a book that is currently unavailable. Implement logic to notify the user when the book becomes available.
2. **/books/{bookId}/cancel-reservation:** Allow users (CUSTOMER) to cancel a book reservation. Update the reservation status accordingly.

### Book Reviews and Ratings
1. **/books/{bookId}/reviews:** Retrieve reviews and ratings for a specific book by bookId.
2. **/books/{bookId}/reviews/create:** Allow users (CUSTOMER) to create a review and rating for a book.
3. **/books/{bookId}/reviews/{reviewId}/update:** Allow users (CUSTOMER) to update their own review and rating for a book.
4. **/books/{bookId}/reviews/{reviewId}/delete:** Allow users (CUSTOMER) to delete their own review and rating for a book.

### User History (Optional)
1. **/users/{userId}/history:** Allow users to view their borrowing history, including borrowed books, due dates, and return dates.

## Technologies Used
- Java Spring Boot
- Spring Security
- MySQL

## Getting Started
To run this application locally, you need to set up the necessary database and configure the application properties. Follow these steps in the project's root directory:
1. Clone the repository.
2. Configure the database connection in `application.properties`.
3. Build and run the project.

## Usage
After setting up the project, you can use tools like Postman to interact with the RESTful endpoints provided by the application.

## Contributors
- [Md. Moien Uddin]
