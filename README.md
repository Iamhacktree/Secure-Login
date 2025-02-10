# Spring Boot Authentication with React Frontend

This project is a full-stack authentication system using **Spring Boot (with Spring Security and MongoDB)** for the backend and **React.js** for the frontend.

## Features

- User authentication (Login & Logout)
- OAuth2 login (Google)
- JWT-based authentication (if needed in the future)
- Role-based access control
- Secure password hashing with BCrypt
- CORS configuration for frontend-backend communication
- Spring Security for authentication and authorization

## Technologies Used

### Backend:

- **Spring Boot**
- **Spring Security**
- **MongoDB Atlas**
- **OAuth2**
- **BCrypt Password Encoder**

### Frontend:

- **React.js**
- **React Router**
- **Tailwind CSS** (for styling)

## Installation & Setup

### Backend (Spring Boot Application)

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
   ```
2. Configure MongoDB Atlas in `application.properties` or `application.yml`.
3. Run the Spring Boot application:
   ```sh
   mvn spring-boot:run
   ```
   The backend server will run at `http://localhost:8080/`.

### Frontend (React Application)

1. Navigate to the frontend directory:
   ```sh
   cd frontend
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Start the React development server:
   ```sh
   npm run dev
   ```
   The frontend will run at `http://localhost:5173/`.

## API Endpoints

| Endpoint                       | Method | Description         |
| ------------------------------ | ------ | ------------------- |
| `/auth/login`                  | POST   | User login          |
| `/auth/logout`                 | GET    | Logout user         |
| `/oauth2/authorization/google` | GET    | OAuth2 Google login |

## CORS Configuration

Ensure that the backend allows cross-origin requests from `http://localhost:5173`. This is configured in `AppSecurityConfig.java`:

```java
@Bean
public CorsConfigurationSource corsConfigurationSource() {
    CorsConfiguration configuration = new CorsConfiguration();
    configuration.setAllowedOrigins(List.of("http://localhost:5173"));
    configuration.setAllowedMethods(List.of("GET", "POST", "PUT", "DELETE", "OPTIONS"));
    configuration.setAllowedHeaders(List.of("Authorization", "Content-Type"));
    configuration.setAllowCredentials(true);
    UrlBasedCorsConfigurationSource source = new UrlBasedCorsConfigurationSource();
    source.registerCorsConfiguration("/**", configuration);
    return source;
}



## Screenshots

### Login Page
```![Screenshot 2025-02-10 194948](https://github.com/user-attachments/assets/6d7ff60f-a805-4e8a-81f8-ccd5cf487302)


### Home Page
```![Screenshot 2025-02-10 195137](https://github.com/user-attachments/assets/94e0f6c4-8477-4ab0-ac78-dfa7b3eed2c4)

![Screenshot 2025-02-10 195008](https://github.com/user-attachments/assets/6458f32c-ce73-41a5-805f-2a8ea29e95c2)


### OAuth2 Login
```![Screenshot 2025-02-10 195137](https://github.com/user-attachments/assets/94e0f6c4-8477-4ab0-ac78-dfa7b3eed2c4)



> Make sure to add screenshots inside the `screenshots/` directory before pushing to GitHub.

## Contribution

Feel free to contribute by submitting a pull request or opening an issue.

## License

This project is licensed under the MIT License.

---

### Author: **Your Name**

GitHub: [yourusername](https://github.com/yourusername)

