# Foreign Language Camp - Server 🖥️

[Live Demo](https://summer-season.vercel.app/)

This is the backend server for the **Foreign Language Camp** project, providing RESTful APIs for user management, class management, enrollment, and payment processing.

---

## Overview
The server is built using **Node.js**, **Express**, and **MongoDB**, with **JWT authentication** for secure user access. It handles all backend operations including:

- User registration and role management (Admin, Instructor, Student)  
- Class management (add, update, feedback, enroll)  
- Payment processing via **Stripe**  
- Secure access using JWT  
- Role-based private routes  

---

## Tech Stack 🛠️
- **Backend:** Node.js, Express  
- **Database:** MongoDB (Atlas)  
- **Authentication:** JWT  
- **Payment:** Stripe  
- **Middleware:** CORS, dotenv  
- **Dependencies:** `express`, `mongodb`, `jsonwebtoken`, `cors`, `stripe`, `dotenv`  

---

## Installation & Setup 🚀

1. **Clone the repository:**
```bash
git clone https://github.com/your-username/foreign-language-camp-server.git
cd foreign-language-camp-server


2. **Install dependencies:**
```bash
npm install
```

3. **Add your Firebase configuration in an .env file:**
```bash
PORT=5000
DB_USER=your_mongodb_user
DB_PASS=your_mongodb_password
JWT_ACCESS_TOKEN_SECRET=your_jwt_secret
PAYMENT_SECRET_KEY=your_stripe_secret_key

```

4. **Start the development server:**
```bash
npm start
```

#### API Endpoints 📡
###### Auth & Users
- POST /jwt – Generate JWT token

- GET /users – Get all users

- POST /users – Add a new user

- PATCH /users/admin/:id – Make a user admin

- PATCH /users/instructor/:id – Make a user instructor

- GET /users/admin/:email – Check if user is admin

- GET /users/instructor/:email – Check if user is instructor

###### Classes
- GET /addClasses – Get all classes

- POST /addClasses – Add a new class
- PATCH /addClasses/:id – Update class status (Admin)

- PUT /addClasses/:id – Add feedback to class

###### Instructor
- GET /instructors – Get all instructors

- GET /instructorClass?email={email} – Get classes of a specific instructor

###### Selected Classes (Student)
- POST /selectedClass – Select a class

- GET /selectedClass?email={email} – Get student's selected classes

- GET /selectedClass/:id – Get single selected class

- DELETE /selectedClass/:id – Cancel selected class

###### Payment
- POST /create-payment-intent – Create Stripe payment intent

- POST /payments – Process payment and update enrolled classes

- GET /studentsPaymentsHistory?email={email} – Get payment history

###### Enrolled Classes
- GET /enrolledClass?email={email} – Get student's enrolled classes

#### Middleware 🔒
**verifyJWT – Verifies JWT token for protected routes**

**verifyAdmin – Ensures the user is an admin**

**verifyInstructor – Ensures the user is an instructor**

#### License 📄
**This project is licensed under the MIT License – see the LICENSE file for details.**

##### Contact ✉️
Email: supto50showrab@gmail.com

Portfolio: https://showrab-paul-portfolio.vercel.app/

