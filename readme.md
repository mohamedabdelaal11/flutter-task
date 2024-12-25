
# Flutter Senior Developer Task Document

## Objective
Integrate a phone login feature into a Flutter application, including UI components and service integration. The flow should cover:
1. **Login with Phone Number**
2. **OTP Verification**
3. **Navigate to Home View**

---

## Requirements

### Functional Requirements
1. **Phone Number Login:**
   - Input field for the phone number.
   - Submit button to send the phone number to the backend service.

2. **OTP Verification:**
   - Input field for entering the OTP received.
   - Submit button to verify the OTP.
   - Show loading or error states based on the verification response.

3. **Home View Navigation:**
   - On successful OTP verification, navigate to the home view.

---

### Non-Functional Requirements
- Ensure smooth transitions between screens.
- Handle API errors gracefully (e.g., invalid OTP, network issues).
- Follow Flutter best practices for state management.
- Code should be modular and maintainable, adhering to clean architecture principles.

---

## Deliverables
1. **UI Integration:**
   - Implement UI for phone number login, OTP verification, and home view.

2. **Service Integration:**
   - Connect the UI to the backend API for login and OTP verification.
   - Use a mock service if the backend is not available.

3. **Clean Architecture Implementation:**
   - Separate the app into distinct layers: **Presentation**, **Domain**, and **Data**.
   - Use repositories to abstract data sources (e.g., APIs, local storage).
   - Implement use cases to handle business logic independently of UI and data sources.

4. **Code Documentation:**
   - Comment critical sections of the code for better understanding.
   - Provide a README file explaining the implementation and how to run the project.

5. **Error Handling:**
   - Display user-friendly error messages for any issues during login or OTP verification.

---

## Flow Diagram
1. User enters the phone number -> Sends request to the backend.
2. Backend sends OTP -> User enters OTP.
3. User submits OTP -> OTP verification succeeds -> Navigate to Home View.

---

## Implementation Details

### UI Screens
[Figma](https://www.figma.com/design/CA07e58FU5PE4k7OIpXL2h/seed?node-id=0-1&p=f)
- **Login Screen:**
  - Input field for phone number.
  - Button to send the number to the backend.
- **OTP Screen:**
  - Input field for OTP.
  - Button to submit OTP for verification.
- **Home Screen:**
  - Placeholder screen to confirm successful login.

### API Endpoints
[Postmam](Integration.postman_collection.json)

1. **Login API:**
   - Endpoint: `/client-api/v1/auth/login`
   - Method: POST
   - Request Body: `{ "phone": "0512345678" }`
   - Response: `{ "success": true, ********** }`

2. **OTP Verification API:**
   - Endpoint: `/client-api/v1/auth/verify-otp`
   - Method: POST
   - Request Body: `{ "phone": "0512345678", "otp": "1234" }`
   - Response: `{"status": 200,"message": "عملية ناجحة"}`

### Clean Architecture Layers
- **Presentation Layer:**
  - Widgets and state management for UI.
- **Domain Layer:**
  - Use cases and entities.
  - Example Use Case: `VerifyOtpUseCase` to handle OTP verification logic.
- **Data Layer:**
  - Repositories and data sources (e.g., REST API, local storage).
  - Example Repository: `AuthRepository` to manage login and OTP verification APIs.

---

## Timeline
- **Day 1-2:**
  - Design UI screens and set up navigation.
  - Implement phone number login UI.
  - Integrate OTP verification UI.
  - Implement mock API services.
  - Apply clean architecture principles.
  - Connect UI to real backend APIs.
  - Implement error handling.
  - Prepare documentation and README.

---

## Additional Notes
- Use appropriate Flutter packages like `http` for API calls or `dio` for advanced features.
- Follow Material Design guidelines for UI components.
- Ensure responsiveness across different screen sizes.
- Refer to the Figma design for UI implementation consistency.

---

## Questions or Clarifications
For any questions, reach out to the project manager or backend team for API details and support.
