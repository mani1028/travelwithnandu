# **🚖 Travel With Nandu \- Intercity Cab & Ambulance Platform**

**Travel With Nandu** is a full-stack web application designed as an aggregator platform for intercity travel between **Karimnagar** and **Hyderabad**. The platform facilitates booking for Shared Rides, Private Cabs, and Emergency Ambulance services.

It features a mobile-first Progressive Web App (PWA) for customers, a landing page for driver partners, and a comprehensive Admin Dashboard for fleet management and analytics.

## **🌟 Key Features**

### **📱 Customer App (PWA)**

* **Authentication:** Secure Login/Signup using Mobile OTP (Firebase Auth).  
* **Multi-Service Booking:**  
  * **Shared Rides:** Book individual seats in Innovas/Ertigas.  
  * **Private Cabs:** Rent full Sedans or SUVs.  
  * **Ambulance:** 24/7 Emergency booking (Basic & Ventilator support).  
* **Live Tracking:** Real-time status updates (Pending \-\> Assigned \-\> Started \-\> Completed).  
* **Profile Management:** Edit details, view ride history, and rate drivers.  
* **Support:** Built-in chat interface and ticket raising system.

### **🛡️ Admin Dashboard**

* **Live Operations:** Monitor active bookings and force-cancel orders if necessary.  
* **Driver Management:** Verify driver documents (License, RC, Insurance) and block/unblock drivers.  
* **Customer Database:** View registered users and chat links.  
* **Analytics:** Visual charts for Revenue trends and Service splits (Chart.js).  
* **Settings:** Control Surge Pricing multipliers and send broadcast messages to drivers.

### **🤝 Partner Portal**

* Informational landing page for onboarding new drivers.  
* Earnings calculator and app download links.

## **🛠️ Tech Stack**

* **Frontend:** HTML5, JavaScript (ES6+ Modules).  
* **Styling:** [Tailwind CSS](https://tailwindcss.com/) (via CDN).  
* **Icons:** [Lucide Icons](https://lucide.dev/).  
* **Backend / Database:** [Google Firebase](https://firebase.google.com/) (v11.6.1).  
  * **Authentication:** Phone Auth & Email/Password (Admin).  
  * **Firestore:** Real-time NoSQL database.  
* **Charts:** [Chart.js](https://www.chartjs.org/).

## **📂 Project Structure**

/  
├── index.html            \# Landing Page (Marketing)  
├── app.html              \# Main Web App (Booking Logic)  
├── partner.html          \# Driver Partner Information  
├── admin.html            \# Admin Dashboard  
├── terms.html            \# Terms of Service  
├── privacy-policy.html   \# Privacy Policy  
└── firebase-config.js    \# Firebase Configuration file

## **🚀 Getting Started**

### **Prerequisites**

1. A code editor (VS Code recommended).  
2. A Google Firebase account.  
3. A local development server (e.g., Live Server extension for VS Code) is required due to ES Module imports and CORS policies.

### **Installation**

1. **Clone the repository:**  
   git clone \[https://github.com/mani1028/travelweb](https://github.com/mani1028/travelweb)  
   cd travel-with-nandu

2. **Firebase Setup:**  
   * Create a new project in the [Firebase Console](https://console.firebase.google.com/).  
   * Enable **Authentication**:  
     * Turn on **Phone Number** sign-in (for Users).  
     * Turn on **Email/Password** sign-in (for Admin).  
   * Create a **Firestore Database**.  
   * Copy your web app configuration keys.  
3. **Configure the App:**  
   * Open firebase-config.js.  
   * Replace the firebaseConfig object with your own credentials:

export const firebaseConfig \= {  
  apiKey: "YOUR\_API\_KEY",  
  authDomain: "YOUR\_PROJECT\_ID.firebaseapp.com",  
  projectId: "YOUR\_PROJECT\_ID",  
  storageBucket: "YOUR\_PROJECT\_ID.appspot.com",  
  messagingSenderId: "YOUR\_SENDER\_ID",  
  appId: "YOUR\_APP\_ID"  
};

4. **Run the App:**  
   * Open the folder in VS Code.  
   * Right-click index.html (or app.html) and select **"Open with Live Server"**.

## **🗄️ Database Structure (Firestore)**

To ensure the app functions correctly, the following collections are used:

| Collection Name | Document ID | Description |
| :---- | :---- | :---- |
| artifacts/{APP\_ID}/public/data/bookings | orderId | Stores all ride bookings. |
| artifacts/{APP\_ID}/public/data/user\_profiles | phoneNumber | Stores customer profiles. |
| artifacts/{APP\_ID}/drivers | driverId | Stores driver details, location, status, and docs. |
| artifacts/{APP\_ID}/settings | config | Stores global settings (e.g., surgeMultiplier). |
| artifacts/{APP\_ID}/support\_tickets | auto-id | Stores user complaints/issues. |

**Note:** The code uses a namespaced structure under artifacts/travel-nandu-v1/... to organize data.

## **🔐 Admin Access**

To access admin.html:

1. Create an admin user in your Firebase Authentication tab (Email/Password).  
2. Open admin.html in your browser.  
3. Login with those credentials.

## **📱 Screenshots**

| Landing Page | Booking App | Admin Dashboard |
| :---- | :---- | :---- |
| *(Add screenshot of index.html)* | *(Add screenshot of app.html)* | *(Add screenshot of admin.html)* |

## **🤝 Contributing**

Contributions are welcome\! Please follow these steps:

1. Fork the repository.  
2. Create a new branch (git checkout \-b feature/AmazingFeature).  
3. Commit your changes (git commit \-m 'Add some AmazingFeature').  
4. Push to the branch (git push origin feature/AmazingFeature).  
5. Open a Pull Request.

## **📄 License**

This project is licensed under the MIT License \- see the [LICENSE](https://www.google.com/search?q=LICENSE) file for details.

**Built with ❤️ for Telangana**
