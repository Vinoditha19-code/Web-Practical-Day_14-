# Web-Practical-Day_14-

It initializes an Express server running on port 3001.
It connects to a MongoDB database named studentInfoDB.
It imports three route files: courseRoute, degreeRoute, and courseRoute (though studentRoute seems mistakenly pointing to courseRoute again).
It attempts to set up routes using app.use(), but the route paths ('./course') should not have a dot (.) before the slash; it should be '/course'.

Defines a courseSchema with fields: code, name, credits, and description.
Creates a Mongoose model Course, linked to the "courses" collection.
Initializes a course entry (webservice) with sample data, but does not save it (the .save() function is commented out).
Exports the Course model for use elsewhere in the application.

GET / → Retrieves all courses from the database. Returns JSON data or a "No data found" message if the database is empty.
GET /:id → Fetches a specific course by its unique ID. Returns course details if found; otherwise, responds with a "No data found" message.
GET 'code/:cid' → Attempts to fetch courses based on their code, but there is an issue:
The route path is missing a leading /, so it won’t function correctly.
Also, the check if (results == null) is incorrect—it should be if (!results || results.length === 0) to properly handle empty results.

Creates a courseSchema with fields _id, name, credits, description, and faculty.
Defines a Mongoose model named Degree, linked to the "degrees" collection.
Creates a sample degree entry (BIT) with details about a Bachelor of Information Technology (BIT) program.
The .save() function is commented out, meaning the degree entry won't be saved unless uncommented.
Exports the Degree model for use elsewhere.


 
 
 
