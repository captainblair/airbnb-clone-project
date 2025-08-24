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

