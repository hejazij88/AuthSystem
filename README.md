# ASP.NET Core Identity with Email Confirmation using SendGrid

This project is a simple implementation of user registration and login functionality using **ASP.NET Core Identity**, with **email confirmation** via **SendGrid**.

## 🔧 Features

- User registration and login using ASP.NET Core Identity
- Email confirmation before login (optional configurable)
- Integration with SendGrid to send confirmation emails
- Secure password hashing and validation
- Razor Pages UI (can be extended to MVC or Blazor)

## 📦 Technologies Used

- ASP.NET Core 7 / 8
- Identity Framework
- Razor Pages
- SendGrid Email API
- Entity Framework Core (SQLite / SQL Server)
- Dependency Injection, Logging

## 🛠️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/hejazij88/AuthSystem.git
cd AuthSystem
2. Configure SendGrid
Create a free SendGrid account and obtain an API key.

Then in appsettings.json, add your SendGrid credentials:

json
Copy
Edit
"SendGrid": {
  "ApiKey": "your-sendgrid-api-key",
  "SenderEmail": "verified-sender@example.com",
  "SenderName": "Your App Name"
}
3. Apply Migrations and Run
Use the .NET CLI or Package Manager Console to apply the database migration:

bash
Copy
Edit
dotnet ef database update
dotnet run
The app will launch on https://localhost:5001.

📧 Email Confirmation Flow
User registers with their email.

A confirmation link is sent to their email via SendGrid.

Until the email is confirmed, login is restricted (if enabled in settings).

After confirmation, the user can log in normally.

✅ Optional Configuration
You can enable or disable the requirement for confirmed accounts in Program.cs:

csharp
Copy
Edit
options.SignIn.RequireConfirmedAccount = true; // or false
📁 Project Structure
markdown
Copy
Edit
/Areas/Identity/Pages/Account/
    - Register.cshtml
    - Register.cshtml.cs
    - ConfirmEmail.cshtml
    - Login.cshtml
/Services/
    - EmailSender.cs
appsettings.json
Program.cs
