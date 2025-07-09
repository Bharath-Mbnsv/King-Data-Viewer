# King-Data-Viewer

# **Data Viewer**

## **Project Overview**
Data Viewer is a web-based application designed to display, filter, sort, and paginate data retrieved from an API. The solution is implemented with both backend and frontend components, ensuring clean architecture, performance, and scalability.

---

## **Features**
1. **Data Display:**
   - Displays `id`, `name`, `status`, `description`, `delta`, and `createdOn` fields in a tabular format.
2. **Sorting:**
   - Supports sorting by `id`, `name`, and `createdOn` in ascending or descending order.
3. **Filtering:**
   - Filter data by `name` (partial match).
   - Filter data by `status` (e.g., `COMPLETED`, `ERROR`).
4. **Pagination:**
   - Displays 20 rows per page with `Next` and `Previous` navigation.
   - Handles large datasets efficiently.
5. **Search & Filter Integration:**
   - Filters and search criteria work independently and in combination.

---

## **Tech Stack**
### **Backend**
- **Language:** Java (version 21)
- **Framework:** Spring Boot
- **Build Tool:** Gradle
- **Testing:** JUnit 5, MockMvc

### **Frontend**
- **Framework:** React with TypeScript
- **State Management:** React Hooks
- **Testing:** React Testing Library
- **Styling:** CSS (custom styles for alignment)

---

## **Folder Structure**
### **Backend**
```plaintext
backend/
├── src/
│   ├── main/
│   │   ├── java/com/king/backend/
│   │   │   ├── controller/         # REST API controllers
│   │   │   ├── service/            # Business logic
│   │   │   ├── utils/              # Helper functions
│   │   │   └── model/              # Data models
│   │   └── resources/
│   │       └── application.properties  # Backend configuration
├── build.gradle                     # Gradle build file
```

### **Frontend**
```plaintext
frontend/
├── src/
│   ├── components/                  # Reusable React components
│   │   ├── DataTable.tsx
│   │   ├── SearchBar.tsx
│   │   ├── Pagination.tsx
│   ├── services/                    # API interaction
│   │   └── api.ts
│   ├── styles/                      # Styling
│   │   └── styles.css
│   ├── utils/                       # Helper functions
│   ├── App.tsx                      # Main application
│   └── index.tsx                    # Application entry point
├── package.json                     # Project dependencies and scripts
```

---

## **Key Decisions and Approach**

1. **Backend Architecture:**
   - **Separation of Concerns:** Divided logic into `controller`, `service`, and `utils` layers to ensure maintainability.
   - **Flexible Filtering:** Implemented independent search and filter logic.
   - **Sorting by CreatedOn:** Handles ISO 8601 dates while ensuring invalid dates are sorted last.

2. **Frontend Architecture:**
   - **Reusable Components:** `SearchBar`, `Pagination`, and `DataTable` are modular and reusable.
   - **Dynamic Sorting and Filtering:** Integrated with backend APIs to minimize frontend complexity.

3. **Performance Considerations:**
   - **Backend:** Lazy loading with pagination to handle large datasets.
   - **Frontend:** Added lazy loading for components using `React.Suspense`.

4. **Code Quality:**
   - Used **TypeScript** for type safety in the frontend.
   - Added comprehensive unit tests for both backend and frontend.

---

## **Installation Instructions**

### **Backend**
1. Navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Build the project:
   ```bash
   ./gradlew build
   ```
3. Run the backend server:
   ```bash
   ./gradlew bootRun
   ```
4. Verify the API is running:
   - Visit [http://localhost:8080/api/data](http://localhost:8080/api/data)

### **Frontend**
1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm start
   ```
4. Open the application in your browser:
   - Visit [http://localhost:3000](http://localhost:3000)

---

## **Testing Instructions**

### **Backend Tests**
1. Run all backend tests:
   ```bash
   ./gradlew test
   ```
2. View test results:
   Open `backend/build/reports/tests/test/index.html` in your browser.

### **Frontend Tests**
1. Run all frontend tests:
   ```bash
   npm test
   ```
2. Generate a test coverage report:
   ```bash
   npm test -- --coverage
   ```
3. Open the coverage report:
   - File location: `frontend/coverage/lcov-report/index.html`


