# Your Money, Your Life

![Project Status](https://img.shields.io/badge/status-completed-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

A modern and responsive web application for personal financial analysis and control, built with pure JavaScript and integrated with Firebase services. It allows users to manage their income and expenses intuitively, featuring visual and detailed dashboards.

---

## Main Features

* **Secure Authentication:** Complete Login, Signup, Password Recovery, and "Show Password" option.
* **Cloud Data Persistence:** All transactions are securely saved to each user's account using Firestore, allowing access from multiple devices (mobile, computer, etc.).
* **Navigable Sidebar:** A professional and expandable sidebar menu to navigate between different sections of the application.
* **Complete Dashboard:** Financial overview with balance, transaction history, and form for new entries.
* **Period Analysis:** Easily switch between **Monthly** and **Yearly** views of your data across all dashboards.
* **Category Dashboards:** Dedicated screens for each income and expense category, with specific charts and histories.
* **Interactive Charts:** Visualize your data with multiple chart types, including Column, Bar, Line, and Pie charts.
* **Responsive Design:** Fully adaptable interface for a seamless experience on both desktops and mobile devices.
* **Modern Interface:** Clean and intuitive design with custom modals for confirmations and interactions, avoiding standard browser alerts.

## Technologies Used

* **Frontend:** HTML5, CSS3, JavaScript (ES6 Modules)
* **Backend & Database:** Google Firebase
    * **Firebase Authentication:** For user management.
    * **Firestore Database:** For real-time data storage.
    * **Firebase Hosting:** For project deployment and hosting.
* **Charts:** [Chart.js](https://www.chartjs.org/)
* **Icons:** [Font Awesome](https://fontawesome.com/)

## Getting Started

To run this project locally, follow the steps below.

### Prerequisites

* You need to have [Node.js](https://nodejs.org/) installed to use `npm`.
* You need to have [Firebase Tools](https://firebase.google.com/docs/cli) installed globally:
    ```bash
    npm install -g firebase-tools
    ```

### Installation and Configuration

1. **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repository.git](https://github.com/your-username/your-repository.git)
    cd your-repository
    ```

2. **Create and configure your Firebase project:**
    * Create a new project in the Firebase Console.
    * Enable **Authentication** services (with the "Email/Password" provider) and **Firestore Database**.
    * When creating Firestore, start in **Production Mode** and choose the closest location (e.g., `southamerica-east1`).
    * In the **Rules** tab of Firestore, paste security rules to allow only logged-in users to access their own data.
    * Copy the `firebaseConfig` object from "Project Settings" and paste it at the top of the `main.js` file.

3. **Create Firestore Indexes:**
    * Run the application locally.
    * Open the browser **Console** (F12).
    * Navigate through the dashboards. The console will show errors with links for the automatic creation of the necessary **indexes**. Click those links and create the indexes in Firebase.

4. **Run the project locally:**
    * The simplest way is to use a VS Code extension like **"Live Server"**. Right-click your `index.html` file and select "Open with Live Server".

5. **To deploy the project:**
    ```bash
    firebase deploy
    ```

## Project Structure

```text
/
├── public/
│   ├── index.html       # Main page structure
│   ├── style.css        # Main stylesheet
│   └── main.js          # Main application logic
├── firestore.rules      # Database security rules
├── firestore.indexes.json # Database index definitions
├── firebase.json        # Firebase project configurations
└── README.md            # This file
