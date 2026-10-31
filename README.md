# oms-expense-manager
Expense manager is a full-stack personal expense management application built using Angular, Java Spring Boot, and MongoDB. It helps users track daily expenses, manage transactions, filter expenses by category and date, and view spending summaries through an intuitive dashboard.
Expense Manager – Full Stack Mini Project
A responsive expense tracking application built with Angular, Java 17, Spring Boot and MongoDB.

Features
Create, view, update and delete expenses
Filter by category and date range
Server-side pagination
Category-wise spending summary
Dashboard totals and responsive UI
Bean validation and centralized REST exception handling
Architecture
Angular UI (4200) → Spring Boot REST API (8080) → MongoDB (expense_manager)

Prerequisites
Java 17+
Maven 3.8+
Node.js 20+ and npm
Angular CLI 19 (npm install -g @angular/cli@19)
MongoDB Community Server running locally, or a MongoDB Atlas connection string
Run MongoDB
Local MongoDB default connection is mongodb://localhost:27017/expense_manager. Start your MongoDB service before starting the API. For Atlas or another server, set MONGODB_URI to your connection string.

Run backend
cd backend
mvn clean spring-boot:run
API base URL: http://localhost:8080/api/expenses

Run frontend (new terminal)
cd frontend
npm install
npm start
Open http://localhost:4200.

REST API reference
Method	Endpoint	Purpose
POST	/api/expenses	Create an expense
GET	/api/expenses?page=0&size=8	List expenses (paginated)
GET	/api/expenses?category=Food&from=2026-10-01&to=2026-10-31	Filter expenses
GET	/api/expenses/summary	Category-wise totals
GET	/api/expenses/{id}	Get one expense
PUT	/api/expenses/{id}	Update an expense
DELETE	/api/expenses/{id}	Delete an expense
Example POST body:

{
  "date": "2026-10-31",
  "category": "Food",
  "amount": 450.50,
  "notes": "Lunch with team"
}
Suggested demo flow
Add expenses in Food, Travel and Bills categories.
Confirm the dashboard and category bars update.
Filter by category and date range.
Edit an expense and verify the changed amount.
Delete an expense and verify the totals update.
Add more than eight records to demonstrate pagination.
Before submission
Run both applications locally and test every flow.
Add screenshots to a screenshots/ folder.
Update this README with your name, project date and any environment-specific setup.
Push the complete expense-manager folder to a new GitHub repository.
Notes / next improvements
For a production system, implement MongoDB aggregation for category summaries (instead of loading a capped page), authentication/authorization, audit fields, automated integration tests, environment-based API URLs, and Docker Compose. The current project is a focused MVP for the assignment.

CORS note
The backend allows API calls from local Angular development origins on localhost and 127.0.0.1 at any port. This supports Angular when it starts on an alternate port (for example, 49155 because port 4200 is occupied). For production deployment, replace this with the exact trusted frontend origin.
