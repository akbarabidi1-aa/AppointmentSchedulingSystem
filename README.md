 Smart Appointment Scheduling System with AI Analysis

A full-stack web application built with **.NET 8** that allows patients to book appointments with doctors. The system features an integrated **Artificial Intelligence (AI)** module using **ML.NET** that predicts the probability of a patient missing their appointment based on their history and the time of day.

 Key Features

*   **Smart Risk Analysis (AI):** Uses a Logistic Regression Machine Learning model to analyze booking details and flag appointments as "High Risk" or "Low Risk" of attendance.
*   **User Authentication:** Secure Login and Registration system with Session management.
*   **Appointment Booking:** Interactive flow to select Doctors and available Time Slots.
*   **Modern UI:** Responsive design using Bootstrap 5, custom CSS gradients, and floating cards.
*   **Database Management:** Stores Doctors, Patients, and Appointments in **SQL Server** using **Entity Framework Core**.

 Tech Stack

*   **Framework:** ASP.NET Core 8.0 (MVC)
*   **Language:** C#
*   **Database:** MS SQL Server (Entity Framework Core)
*   **Machine Learning:** ML.NET (Microsoft.ML)
*   **Frontend:** Razor Views (.cshtml), HTML5, CSS3, Bootstrap 5

How the AI Works

The project uses `ML.NET` to train a model (`DoctorPatientML.zip`) based on historical data.
1.  **Inputs:** It looks at the patient's previous `Attended` vs. `Missed` counts, the `Hour` of the appointment, and the `DayOfWeek`.
2.  **Prediction:** When a patient confirms a booking, the system calculates a probability score.
3.  **Result:**
    *   **Score < 0.5:** System flags as **🔥 High Risk** (Red Badge).
    *   **Score > 0.5:** System flags as **🛡️ Low Risk** (Blue Badge).

How to Run Locally

1.  **Clone the repository** to your local machine.
2.  **Update Database Connection:**
    *   Open `appsettings.json` and check the connection string (ensure it points to your local SQL Express instance).
3.  **Create the Database:**
    *   Run `Update-Database` in the Package Manager Console OR run the SQL script provided to create tables (`Doctors`, `Patients`, `Appointments`).
4.  **Generate the AI Model:**
    *   Uncomment the `MLTrainer.Train()` line in `Program.cs` and run the app **once** to generate the `DoctorPatientML.zip` file.
    *   Comment the line out again after the file is created.
5.  **Run the Application:**
    *   Press `F5` or `Ctrl+F5` in Visual Studio.

 License

This project is for educational purposes.
