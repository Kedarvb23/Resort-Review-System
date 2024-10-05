# Resort-Review-System
#### Video Demo : https://youtu.be/5zt5_U9ZT1Q
#### Description:
The Resort Review System is a full-stack web application designed to let users browse, rate, and review resorts. It draws inspiration from the YelpCamp project by Colt Steele but is customized to focus on resorts rather than campgrounds. The system is built using modern web development technologies, such as Node.js, Express, MongoDB, and Bootstrap, and follows a RESTful architecture to provide a seamless user experience.

This application allows users to register, log in, browse resorts, view detailed information about each resort, and leave reviews or ratings for them. Each resort can have multiple reviews, and users can contribute their opinions to help others make informed decisions when choosing their next getaway destination. Additionally, authorized users have the ability to create, update, and delete resort listings, giving them full control over the content of the site.

Key Features:
- User authentication and authorization with Passport.js
- CRUD functionality for resorts (Create, Read, Update, Delete)
- Review and rating system for resorts
- Dynamic map integration with Mapbox for displaying resort locations
- Responsive design for mobile and desktop using Bootstrapp
File Descriptions :
1. app.js
The app.js file is the entry point for the entire application. It initializes the Express server, sets up middleware, connects to the MongoDB database, and configures routes. Key functionalities include:

- Setting up middleware like express-session, passport, and connect-flash for session management and user authentication.
- Establishing connection to MongoDB using Mongoose.
- Defining routes for resorts and user-related operations.
- Handling error pages for any incorrect routes.
  
2. models/Resort.js
This file defines the schema for resorts using Mongoose. Each resort object in the database consists of attributes such as the resort name, price, location, description, and image URLs. Additionally, the resort schema has a reference to the reviews associated with it, which is handled by a separate model.

3. models/Review.js
The Review.js file defines the review schema, which includes the review content, rating, author, and a reference to the associated resort. This model helps maintain relationships between resorts and reviews, enabling multiple reviews for each resort.

4. routes/resorts.js
This file contains all the route handlers for resort-related operations. It defines routes for viewing all resorts, creating new resorts, editing existing resorts, and deleting resorts. It also includes middleware to check whether the user is logged in and authorized to perform specific actions.

5. routes/reviews.js
This file manages routes for creating, updating, and deleting reviews. It is responsible for ensuring that users can only delete or modify reviews they’ve created, preserving the integrity of the user-generated content on the platform.

6. views/resorts/
This folder contains the EJS templates for rendering resort-related pages. The key templates are:

- index.ejs: Displays a list of all resorts, each with basic details and links to view more information.
- show.ejs: Renders detailed information about a single resort, including user-submitted reviews.
- new.ejs and edit.ejs: Provide forms for adding and updating resort information, respectively.
  
7. views/reviews/
This folder contains templates for managing reviews. The primary file is:

- edit.ejs: A form for editing existing reviews of resorts.
8. views/partials/
This directory holds the partial templates like the header and footer, which are used across multiple pages for consistent design. It also includes the flash messages that alert users about actions like successful login or errors during submission.

9. public/
This folder contains all the static assets, including CSS, JavaScript, and images used across the site. The Bootstrap framework has been customized here to ensure that the site looks modern and responsive.

10. middleware/
Custom middleware functions are stored in this directory. These functions handle tasks like user authentication, authorization checks for edit/delete actions, and validating input before saving it to the database.

11. config/
This folder includes configuration files for connecting to the database, as well as API configurations for services like Mapbox, which is used for dynamic mapping of resort locations.

Design Decisions and Trade-offs
Choice of Frameworks and Tools:
The decision to use Node.js with Express was based on the flexibility and extensive community support available for building robust web applications. MongoDB, combined with Mongoose, provides a non-relational database structure that is particularly well-suited for managing the dynamic nature of reviews and resorts.

CRUD Design:
A major design focus was on ensuring a smooth and intuitive user experience for managing resorts and reviews. The creation, updating, and deletion of resorts and reviews were implemented following RESTful principles, which provide clean and predictable URLs and HTTP methods for different operations.

User Experience:
To enhance the user experience, we decided to integrate dynamic maps using the Mapbox API, which helps users visually locate resorts. Another crucial design choice was making the application fully responsive, ensuring that users can access the site seamlessly across devices, whether on desktop or mobile.

Authentication:
The authentication system was built with Passport.js to manage user sessions and authorization securely. User roles are also factored in to ensure that only the author of a resort or review can modify or delete it, adding a layer of security and trust to user-generated content.

Conclusion
The Resort Review System is a comprehensive platform that provides users with an interactive and informative way to explore resorts, leave feedback, and contribute to the community. With robust CRUD functionality, user authentication, and modern web technologies, this project offers both a technical challenge and a valuable real-world application.
