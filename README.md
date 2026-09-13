# EduPortal🎓

> **Next-Generation Smart Educational Management & AI-Powered Virtual Classroom Platform**

EduPortal is an end-to-end, role-based educational management system engineered with React, TypeScript, Tailwind CSS, shadcn/ui, and real-time **AI Face & Eye-Gaze Attention Tracking** powered by TensorFlow.js.

---

## 🌟 Key Highlights & AI Innovation

- **🤖 AI-Powered Live Attention & Eye-Contact Tracking**: Real-time computer vision using TensorFlow.js and Face Landmark Mesh to track student eye gaze, head pose, and engagement score during virtual live classes.
- **⚡ Automated Constraint-Satisfying Scheduler**: Built-in greedy & optimization solver for automatic university/school timetable generation considering room capacity, room types (Lecture/Lab/Seminar), instructor availability, and section loads.
- **🔐 Multi-Role Access Control**: Secure authentication and custom navigation tailored for **Students**, **Faculty**, and **System Administrators**.
- **📊 Real-Time Analytics & Reporting**: Interactive Recharts dashboards for attendance metrics, student focus trends, and institutional reporting.
- **💾 Dual Persistence Model**: Works seamlessly out-of-the-box with local browser persistence (`localStorage`) or connects to **Supabase** backend infrastructure.

---

## 👥 Role-Based Feature Overview

### 🎓 1. Student Portal
- **Interactive Timetable**: Weekly schedule matrix with live class links and period breakdowns.
- **Live Class Hub & AI Camera Tracking**: Join virtual classes with automated real-time eye-contact focus scoring and attention metrics.
- **Assignments & Resource Downloads**: Upload assignments, track deadlines, and download course study materials.
- **Progress Tracking**: Personal attendance history, grade trends, and focus score logs.

### 👨‍🏫 2. Faculty & Teacher Portal
- **Classroom Management**: View assigned courses, student rosters, and daily schedules.
- **Live Attendance & Focus Dashboard**: Monitor student attention scores and camera state during live lectures.
- **Substitute Teacher Management**: Assign substitute instructors for scheduled periods.
- **Assignment Grading**: Review, evaluate, and provide feedback on student submissions.
- **Class Analytics**: Export detailed attendance and performance reports.

### 🛡️ 3. Administrator Portal
- **System Overview & Health**: Live server metrics, user statistics, and active session metrics.
- **User Management (CRUD)**: Create, edit, search, filter, activate/deactivate, and delete accounts across Student, Faculty, and Admin roles.
- **Role & Permission Customization**: Fine-grained toggle controls for feature access per user role.
- **Automated Timetable Generator Engine**:
  - Configure Departments, Rooms (Capacity & Type), Instructors (Max Load), Courses, Sections, and Time Periods.
  - One-click greedy scheduler engine with live weekly preview grid exportable to JSON/CSV.

---

## 🛠️ Technology Stack

| Domain | Technologies Used |
| :--- | :--- |
| **Core Framework** | [React 18](https://reactjs.org/), [TypeScript](https://www.typescriptlang.org/), [Vite](https://vitejs.dev/) |
| **UI & Styling** | [Tailwind CSS](https://tailwindcss.com/), [shadcn/ui](https://ui.shadcn.com/), [Lucide React Icons](https://lucide.dev/) |
| **State & Routing** | [React Router v6](https://reactrouter.com/), [TanStack React Query v5](https://tanstack.com/query) |
| **AI / Machine Learning** | [TensorFlow.js](https://www.tensorflow.org/js), `@tensorflow-models/face-landmarks-detection`, `@mediapipe/face_mesh` |
| **Data Visualization** | [Recharts](https://recharts.org/) |
| **Backend & Storage** | [Supabase](https://supabase.com/) JS Client + LocalStorage Fallback Layer |

---

## 📂 Project Directory Structure

```text
nav-guard-hub/
├── public/                     # Static assets & public images
├── src/
│   ├── components/             # Reusable UI components
│   │   ├── ui/                 # Radix UI / shadcn/ui component primitives
│   │   ├── AppSidebar.tsx      # Role-aware navigation sidebar
│   │   ├── AttentionDashboard.tsx # AI attention tracking analytics
│   │   ├── SubstituteManager.tsx  # Faculty substitute management
│   │   └── Layout.tsx          # Main application layout wrapper
│   ├── config/
│   │   └── routes.ts           # Centralized route & permission configuration
│   ├── contexts/
│   │   ├── AuthContext.tsx     # Role authentication & user session state
│   │   └── TimetableContext.tsx# Live class & timetable state provider
│   ├── hooks/
│   │   ├── use-toast.ts        # Toast notification system
│   │   └── useAttentionTracking.ts # TensorFlow.js face landmark hook
│   ├── lib/
│   │   ├── api.ts              # Unified API client layer
│   │   └── schedulerDemo.ts    # Algorithmic timetable generator engine
│   ├── pages/                  # Top-level page views
│   │   ├── AdminDashboard.tsx      # System admin control center
│   │   ├── ManageUsersPage.tsx     # Full user administration (CRUD)
│   │   ├── SchedulerAdminPage.tsx  # Timetable generation engine page
│   │   ├── StudentDashboard.tsx    # Student portal home
│   │   ├── FacultyDashboard.tsx    # Faculty control center
│   │   ├── AttendanceTrackingPage.tsx # Live AI camera attendance tracking
│   │   ├── TimetablePage.tsx       # Class schedule viewer
│   │   ├── AssignmentsPage.tsx     # Assignment submission & management
│   │   ├── PermissionsPage.tsx     # Admin permission manager
│   │   ├── ReportsPage.tsx         # Analytical reporting suite
│   │   └── SystemSettingsPage.tsx  # System configurations
│   ├── App.tsx                 # Main application routes & auth guards
│   └── main.tsx                # Application entry point
├── package.json
├── vite.config.ts
└── tailwind.config.ts
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed on your machine:
- **Node.js**: `v18.0.0` or higher
- **npm**: `v9.0.0` or higher

### Installation & Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-org/nav-guard-hub.git
   cd nav-guard-hub
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Configure Environment Variables (Optional)**:
   Create a `.env` file in the project root if connecting to Supabase:
   ```env
   VITE_SUPABASE_URL=https://your-supabase-project.supabase.co
   VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
   VITE_SCHEDULER_DEMO=true
   ```

4. **Start the Local Development Server**:
   ```bash
   npm run dev
   ```
   Open your browser and navigate to `http://localhost:8080` (or the port specified in terminal).

5. **Type Checking & Production Build**:
   ```bash
   # Run TypeScript compilation check
   npx tsc --noEmit

   # Create production build
   npm run build
   ```

---

## 🔑 Demo Access Roles

When launching the app, you can select any of the pre-configured role profiles from the login selector:

| Role Profile | Default Credentials / Selection | Capabilities |
| :--- | :--- | :--- |
| **Student** | Click **Student Login** | Access timetable, submit assignments, join live class with AI gaze tracking |
| **Faculty** | Click **Teacher Login** | Manage classes, review live student focus scores, assign substitutes |
| **Administrator** | Click **Admin Login** | Complete platform access, Manage Users, Configure Scheduler, System Logs |

---

## 🧪 AI Attention Tracking Workflow

1. Navigate to **Live Classes** or **Live Tracking** (`/attendance-tracking`).
2. Grant camera permissions when prompted.
3. The TensorFlow.js face landmark detection model will load automatically.
4. When looking directly at the camera, the system detects eye position and computes a **Real-Time Attention Score** (0% to 100%).
5. Attention events are streamed live to the instructor dashboard.

---

## 📜 License

This project is licensed under the **MIT License**. Feel free to modify and adapt for educational or commercial purposes.
