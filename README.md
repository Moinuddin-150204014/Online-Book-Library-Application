<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Book Library Application</title>
</head>
<body>
    <h1>Online Book Library Application</h1>
    <p>This is a backend-only Online Book Library application that provides REST endpoints for managing users, books, book borrowing and returning, book reservations (optional), book reviews and ratings, and user history (optional). The application uses Spring Security for role-based authentication and MySQL for the database.</p>

    <h2>User Management Endpoints</h2>
    <ul>
        <li><code>/user/register</code>: Register a user with user information (first name, last name, email, password, address).</li>
        <li><code>/user/login</code>: Login with user email and password and return a token as a response.</li>
        <li><code>/users/{userId}</code>: Retrieve user details by userId. Only users with ADMIN roles have access to this API.</li>
        <li><code>/users/{userId}/books</code>: Retrieve the books borrowed or owned by a specific user. Accessible by the user to view their own books or by an ADMIN to view any user's books.</li>
        <li><code>/users/{userId}/borrowed-books</code>: Retrieve the books currently borrowed by a specific user. Accessible by the user to view their own borrowed books or by an ADMIN to view any user's borrowed books.</li>
    </ul>

    <h2>Books Management</h2>
    <ul>
        <li><code>/books/create</code>: Add a new book to the database. User must have the "ADMIN" role to use this API.</li>
        <li><code>/books/update</code>: Update a book's data that is already saved in the database. User must have the "ADMIN" role to use this API.</li>
        <li><code>/books/delete</code>: Delete a book from the database. User must have the "ADMIN" role to use this API.</li>
        <li><code>/books/all</code>: Fetch and show all the books data stored in the database. User must have either "ADMIN" or "CUSTOMER" role to use this API.</li>
    </ul>

    <h2>Book Borrowing/Returning Endpoints</h2>
    <ul>
        <li><code>/books/{bookId}/borrow</code>: Allow users (CUSTOMER) to borrow a book by bookId. Implement logic to track the book's availability and due date.</li>
        <li><code>/books/{bookId}/return</code>: Allow users (CUSTOMER) to return a borrowed book by bookId. Update the book's status accordingly.</li>
    </ul>

    <h2>Book Reservation Endpoints (Optional)</h2>
    <ul>
        <li><code>/books/{bookId}/reserve</code>: Allow users (CUSTOMER) to reserve a book that is currently unavailable. Implement logic to notify the user when the book becomes available.</li>
        <li><code>/books/{bookId}/cancel-reservation</code>: Allow users (CUSTOMER) to cancel a book reservation. Update the reservation status accordingly.</li>
    </ul>

    <h2>Book Reviews and Ratings</h2>
    <ul>
        <li><code>/books/{bookId}/reviews</code>: Retrieve reviews and ratings for a specific book by bookId.</li>
        <li><code>/books/{bookId}/reviews/create</code>: Allow users (CUSTOMER) to create a review and rating for a book.</li>
        <li><code>/books/{bookId}/reviews/{reviewId}/update</code>: Allow users (CUSTOMER) to update their own review and rating for a book.</li>
        <li><code>/books/{bookId}/reviews/{reviewId}/delete</code>: Allow users (CUSTOMER) to delete their own review and rating for a book.</li>
    </ul>

    <h2>User History (Optional)</h2>
    <ul>
        <li><code>/users/{userId}/history</code>: Allow users to view their borrowing history, including borrowed books, due dates, and return dates.</li>
    </ul>

    <p>Please refer to the specific Java classes created for this application according to the requirements.</p>
</body>
</html>
