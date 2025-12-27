# **🚀 Nandu Travels Platform (v3.2)**

⚠️ Release Status: Pre-Release / Beta  
🛑 Testing Status: Partially Tested  
📅 Last Updated: December 27, 2025

## **📝 Overview**

**Travel With Nandu** is a comprehensive travel ecosystem designed to bridge the gap between customers and local travel partners. This repository contains the complete source code for the platform, comprising two main components:

1. **Customer Web App:** A seamless booking interface for users.  
2. **Driver Partner Portal:** A dedicated dashboard for drivers to manage rides and earnings.

The system is built on a serverless architecture using **Google Firebase** (Authentication & Firestore) with a highly responsive, mobile-first frontend powered by **Tailwind CSS**.

## **✨ Key Features**

### **🚗 User Application (index.html)**

The customer-facing application focuses on ease of use, security, and real-time feedback.

* **Authentication & Profile**  
  * **Secure Login:** Mobile number authentication via Firebase Phone Auth (OTP).  
  * **Onboarding:** Streamlined flow for new users to set up their profiles.  
  * **Session Persistence:** Keeps users logged in for a smooth experience.  
* **Advanced Booking Engine**  
  * **Multi-Service Support:**  
    * **Shared Cabs:** Economical 5-Seater & 7-Seater options.  
    * **Private Taxis:** Sedan & SUV (AC/Non-AC variants) for exclusive travel.  
    * **Ambulance Service:** Specialized booking for Basic, Standard (Oxygen), and ICU (Ventilator) ambulances.  
  * **Dynamic Pricing:** Real-time fare estimation algorithm based on route distance, vehicle type, and passenger count.  
  * **Route Logic:** Hard-coded optimizations for core routes (e.g., Karimnagar ⇄ Hyderabad/JBS/Airport).  
* **Real-Time Intelligence**  
  * **Live Availability:** Users can see the exact count of available drivers or seats on their selected route in real-time.  
  * **Smart Fallback:** If a specific requested vehicle isn't available, the system intelligently suggests alternatives (e.g., suggesting a 7-seater if 5-seaters are full).  
  * **Duplicate Detection:** Logic to prevent users from accidentally double-booking or creating conflicting ride requests.  
* **Order Management**  
  * **Live Tracking:** View assigned driver details including Name, Photo, Rating, and Vehicle Number.  
  * **OTP Verification:** Secure "Start Ride" OTP displayed to the user to share with the driver.  
  * **Trip History:** Comprehensive list of Active, Completed, and Cancelled trips.  
  * **Rating System:** Interactive star rating and feedback mechanism for completed rides.  
  * **Cancellation:** User-friendly cancellation flow with specific reason selection.

### **🚕 Driver Partner Portal (driver-portal.html)**

A robust toolset for partners to manage their business efficiently.

* **Onboarding & Identity**  
  * **Registration:** Detailed capture of Vehicle details (Number Plate, Type).  
  * **Partner IDs:** Auto-generation of unique IDs (Format: ID-YYYY-XXXX).  
  * **Profile Management:** Capability to edit contact info and upload profile pictures.  
* **Job Management Dashboard**  
  * **Ride Radar:** Real-time stream of "New Requests" that specifically match the driver's vehicle type and preferred route.  
  * **Smart Filtering:** Jobs are strictly filtered based on the Driver's settings (e.g., "AC Only" or specific "Hubs").  
  * **Trip Workflow:** Full lifecycle management: Accept Job \-\> Verify OTP \-\> Start Trip \-\> Collect Cash \-\> Complete Trip.  
  * **Exception Handling:** Options to report issues like "Customer Not Responding" or "Not Interested" to cancel rides gracefully.  
* **Capacity Management**  
  * **Manual Seat Filler:** Allows drivers to manually log passengers picked up offline, ensuring the platform's availability count remains accurate.  
* **Wallet & Analytics**  
  * **Earnings Tracker:** Visual dashboard displaying income versus expenses.  
  * **Expense Logging:** Tools to manually log operational costs like Fuel, Tolls, and Maintenance.  
  * **Trip Logs:** Detailed history of past trips with financial breakdowns.  
* **Utilities**  
  * **Theme Support:** Built-in Dark Mode and Light Mode.  
  * **Document Upload:** UI for uploading Driving License and Insurance documents.  
  * **Status Toggle:** Online/Offline switch with safety checks to prevent going offline while trips are active.

## **🛠 Technical Stack**

* **Frontend:** HTML5, Vanilla JavaScript (ES6 Modules).  
* **Styling:** Tailwind CSS (via CDN), Lucide Icons for UI elements.  
* **Backend / Database:** Google Firebase Firestore (NoSQL) for real-time data syncing.  
* **Authentication:** Firebase Phone Authentication (with reCAPTCHA verifier).  
* **Deployment:** Ready for Static Web Hosting (e.g., GitHub Pages, Netlify, Firebase Hosting).

## **📦 Deployment Instructions**

To deploy this project to your own environment:

1. **Firebase Configuration:**  
   * Create a project in the [Firebase Console](https://console.firebase.google.com/).  
   * Enable **Authentication** (Phone Provider) and **Firestore**.  
   * Replace the firebaseConfig object in both index.html and driver-portal.html with your project's specific keys.  
   * Update the \_\_app\_id variable to match your desired Firestore collection structure.  
2. **Firestore Rules:**  
   * Set up Firestore security rules to allow read/write access to the /artifacts/{appId}/... path for authenticated users.  
3. **Hosting:**  
   * Deploy index.html as the main entry point (Customer App).  
   * Deploy driver-portal.html as a separate route or within a protected directory (e.g., /partner) for drivers.

## **🐛 Known Issues & Limitations**

* **Concurrency:** High-concurrency booking stress tests have not been performed; race conditions may occur under extremely heavy load.  
* **Payment Integration:** The system currently relies on "Cash on Delivery" logic. Online payment gateway integration is planned for future releases.  
* **Document Verification:** The document upload feature in the driver portal is currently a UI demonstration and does not perform backend file storage or OCR verification.  
* **Edge Cases:** Network interruption handling during critical states (like "Booking Processing") requires further robustness testing.

*Developed with ❤️ for Nandu Travels.*
