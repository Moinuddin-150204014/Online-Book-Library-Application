# Online Book Library Application

This is a backend-only Online Book Library application that provides REST endpoints for managing users, books, book borrowing and returning, book reservations (optional), book reviews and ratings, and user history (optional). The application uses Spring Security for role-based authentication and MySQL for the database.

## User Management Endpoints

1. `/user/register`: Register a user with user information (first name, last name, email, password, address).

2. `/user/login`: Login with user email and password and return a token as a response.

3. `/users/{userId}`: Retrieve user details by userId. Only users with ADMIN roles have access to this API.

4. `/users/{userId}/books`: Retrieve the books borrowed or owned by a specific user. Accessible by the user to view their own books or by an ADMIN to view any user's books.

5. `/users/{userId}/borrowed-books`: Retrieve the books currently borrowed by a specific user. Accessible by the user to view their own borrowed books or by an ADMIN to view any user's borrowed books.

## Books Management

1. `/books/create`: Add a new book to the database. User must have the "ADMIN" role to use this API.

2. `/books/update`: Update a book's data that is already saved in the database. User must have the "ADMIN" role to use this API.

3. `/books/delete`: Delete a book from the database. User must have the "ADMIN" role to use this API.

4. `/books/all`: Fetch and show all the books data stored in the database. User must have either "ADMIN" or "CUSTOMER" role to use this API.

## Book Borrowing/Returning Endpoints

1. `/books/{bookId}/borrow`: Allow users (CUSTOMER) to borrow a book by bookId. Implement logic to track the book's availability and due date.

2. `/books/{bookId}/return`: Allow users (CUSTOMER) to return a borrowed book by bookId. Update the book's status accordingly.

## Book Reservation Endpoints (Optional)

1. `/books/{bookId}/reserve`: Allow users (CUSTOMER) to reserve a book that is currently unavailable. Implement logic to notify the user when the book becomes available.

2. `/books/{bookId}/cancel-reservation`: Allow users (CUSTOMER) to cancel a book reservation. Update the reservation status accordingly.

## Book Reviews and Ratings

1. `/books/{bookId}/reviews`: Retrieve reviews and ratings for a specific book by bookId.

2. `/books/{bookId}/reviews/create`: Allow users (CUSTOMER) to create a review and rating for a book.

3. `/books/{bookId}/reviews/{reviewId}/update`: Allow users (CUSTOMER) to update their own review and rating for a book.

4. `/books/{bookId}/reviews/{reviewId}/delete`: Allow users (CUSTOMER) to delete their own review and rating for a book.

## User History (Optional)

1. `/users/{userId}/history`: Allow users to view their borrowing history, including borrowed books, due dates, and return dates.

Please refer to the specific Java classes created for this application according to the requirements.
