# Amplifi Music Library

Amplifi is a full-stack Next.js music streaming and discovery platform. Originally developed as a collaborative group project, this repository represents an independently refactored and expanded version by Blake Mitchell, specifically tailored to showcase backend architecture, relational database management, and complex data visualization capabilities.

![Amplifi Platform Overview](./public/screenshots/AdminPage.png)

This platform facilitates sophisticated user-to-content interactions, extensive listening analytics, and dynamic administrative control powered by a MySQL database hosted on Microsoft Azure.

## Technical Architecture & Backend Highlights

The platform's infrastructure is built to handle high-volume streaming data, complex relational queries, and dynamic data visualization. My primary contributions and independent refactoring efforts focused on:

*   **Database Architecture & ORM:** Engineered a relational MySQL database utilizing Prisma ORM to manage user authentication, hierarchical content structures (albums and playlists), and continuous playback events. Designed the database seeding scripts to populate and manage the platform's extensive audio catalog.
*   **Interactive Administrative Dashboard:** Developed a secure admin portal allowing for real-time, in-application modifications of user profiles, artist data, and catalog metadata.
*   **Dynamic Analytics Engine:** Implemented highly interactive data visualization using `chart.js` and `recharts`. The dashboard generates real-time relational metrics, platform-wide streaming trends, broad categorical data, and granular individual artist analytics.
*   **Automated PDF Reporting:** Engineered an exportable reporting system using `pdf-lib` that synthesizes streaming data into actionable intelligence. The system generates detailed documents outlining artist rankings alongside data-driven strategies for increasing platform popularity.
    *   📄 **[View the Example Artist Rankings & Strategy Report PDF here](./SampleReport.pdf)**

## Platform Features

**For Administrators**
*   Comprehensive music catalog and metadata management.
*   Deep platform performance monitoring and user listening analytics.
*   Dynamic data visualization and exportable PDF reporting tools.

**For Users**
*   Discover new music based on personalized listening preferences.
*   Create, modify, and share custom playlists.
*   Save favorite songs and albums to a unified personal library.
*   Connect with and follow other users to explore varying music tastes.
*   View personal analytics based on individualized streaming statistics.

![Amplifi Home Screen & Music Discovery Interface](./public/screenshots/HomePage.gif)

**For Artists**
*   Customizable artist profiles featuring music catalogs and biographical information.
*   Access to detailed listener demographics and track streaming statistics.

## Technology Stack

*   **Frontend Framework:** Next.js (v15), React (v19)
*   **Styling & UI:** Tailwind CSS, Shadcn, Framer Motion, Radix UI
*   **State Management:** Zustand
*   **Backend Environment:** Node.js
*   **Database & ORM:** MySQL, Prisma Client (v6)
*   **Data Visualization:** Chart.js, Recharts, Chartjs-plugin-datalabels
*   **Authentication & Security:** Next-Auth, bcrypt
*   **Cloud Storage Integrations:** AWS S3 SDK, Azure Storage Blob
*   **Document Generation:** pdf-lib
*   **Audio Processing:** music-metadata

## Getting Started

To run the Amplifi platform locally for development and testing:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/amplifi.git](https://github.com/yourusername/amplifi.git)
    cd amplifi
    ```

2.  **Install dependencies:**
    Ensure you have Node.js installed on your system, then run:
    ```bash
    npm install
    ```

3.  **Environment Setup:**
    Create a `.env` file in the root directory and configure your environmental variables, including the MySQL database connection string required by Prisma:
    ```env
    DATABASE_URL="mysql://user:password@your-azure-host:3306/amplifi"
    NEXTAUTH_SECRET="your_secret"
    ```

4.  **Database Synchronization:**
    Generate the Prisma client and push the schema to your database:
    ```bash
    npx prisma generate
    npx prisma db push
    ```

5.  **Start the development server:**
    ```bash
    npm run dev
    ```

6.  **Access the application:**
    Open your browser and navigate to [http://localhost:3000](http://localhost:3000).

## Deployment

Amplifi is optimized for serverless deployment on Vercel, utilizing its seamless integration with Next.js for rapid public access and edge routing.