Airbnb Clone project — backend booking system simulation.
Goals: backend learning, scalability, teamwork.

Tech stack: Django, MySQL/PostgreSQL, GraphQL, Docker, GitHub Actions.
                 
                   ## Team Roles

- **Backend Developer** – Builds APIs and backend logic.
- **Database Administrator** – Designs the database schema and manages data.
- **DevOps Engineer** – Handles CI/CD pipelines, deployment, and containerization.
- **QA Engineer** – Tests the system and ensures quality.
- **Project Manager** – Coordinates the team and oversees the project progress.


## Technology Stack

- **Django** – A high-level Python web framework used to build the backend, handle requests, and manage the application logic.
- **MySQL/PostgreSQL** – Relational database systems used to store users, properties, bookings, reviews, and payments data.
- **GraphQL** – A query language for APIs that allows clients to request exactly the data they need.
- **Docker** – A containerization tool used to package the application and its dependencies for consistent deployment.
- **GitHub Actions** – A CI/CD tool used to automate testing, building, and deployment of the application.
- **RESTful APIs** – Standardized APIs for communication between the frontend and backend services.

## Database Design

The database is designed to store and manage all core data for the Airbnb Clone project. The key entities and their fields are as follows:

- **Users**
  - `id`: Unique identifier for each user
  - `name`: Full name of the user
  - `email`: Email address
  - `password`: Hashed password for authentication
  - `role`: User role (e.g., guest, host, admin)

- **Properties**
  - `id`: Unique identifier for each property
  - `owner_id`: References `Users.id` (the property owner)
  - `title`: Property title or name
  - `description`: Short description of the property
  - `location`: Property address or location
  - `price_per_night`: Cost per night

- **Bookings**
  - `id`: Unique identifier for each booking
  - `property_id`: References `Properties.id`
  - `user_id`: References `Users.id`
  - `start_date`: Booking start date
  - `end_date`: Booking end date
  - `status`: Booking status (e.g., confirmed, canceled)

- **Reviews**
  - `id`: Unique identifier for each review
  - `user_id`: References `Users.id`
  - `property_id`: References `Properties.id`
  - `rating`: Numeric rating
  - `comment`: Review text

- **Payments**
  - `id`: Unique identifier for each payment
  - `booking_id`: References `Bookings.id`
  - `amount`: Total payment amount
  - `status`: Payment status (e.g., paid, pending)
  - `method`: Payment method (e.g., card, mobile money)

**Entity Relationships**:
- A user can own multiple properties.
- A booking belongs to a single property and is made by a single user.
- A review is associated with both a user and a property.
- Each payment is linked to a specific booking.


## Feature Breakdown

- **User Management**  
  Allows users to sign up, log in, and manage their profiles. Ensures that only authenticated users can make bookings or manage properties.

- **Property Management**  
  Enables hosts to add, update, and remove properties. Provides essential property details like location, price, and description for potential guests.

- **Booking System**  
  Allows users to book available properties for specific dates. Tracks booking status and prevents double bookings.

- **Review System**  
  Lets users leave ratings and comments for properties they have stayed in. Helps maintain transparency and trust among users.

- **Payment Processing**  
  Handles secure payments for bookings through multiple payment methods. Ensures that funds are correctly tracked and linked to bookings.

## API Security

To ensure the Airbnb Clone backend is secure, the following key measures will be implemented:

- **Authentication**  
  Users must log in using secure credentials (e.g., hashed passwords or JWT tokens). This ensures that only legitimate users can access the system.

- **Authorization**  
  Role-based access control will restrict actions based on user roles (e.g., guest, host, admin). This prevents unauthorized access to sensitive data or actions.

- **Rate Limiting**  
  API requests will be limited to prevent abuse and protect the system from DDoS attacks.

- **Data Validation**  
  All inputs will be validated to prevent attacks such as SQL injection or data corruption.

- **Secure Payments**  
  Payment information will be handled securely to protect user financial data and ensure transactions are trustworthy.

Security is crucial to protect user data, maintain trust, prevent fraud, and ensure the system operates reliably.


