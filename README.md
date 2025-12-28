# HostelManager - Real-Time Hostel Management System

A modern, full-stack, real-time application designed for hostel administrators and students to manage room allocations, complaints, notices, and payments efficiently.

## 🚀 Features

### For Administrators
- **Dashboard**: Live statistics of occupancy, pending complaints, and monthly collections.
- **Room Management**: Add/remove rooms and manage bed occupancy in real-time.
- **Student Management**: Register students and assign them to available beds.
- **Complaint Resolution**: View and respond to student complaints with live status updates.
- **Notice Board**: Post urgent or normal priority notices that sync instantly to all users.
- **Payment Tracking**: Monitor rent payments and filter by status (Paid/Pending/Overdue).

### For Students
- **Real-Time Notices**: Get instant updates on hostel announcements.
- **Complaint Filing**: Raise issues and track the status of resolution.
- **Profile Management**: View assigned room and bed details.

## 🛠 Tech Stack

- **Frontend**: Next.js 14 (App Router), React, Tailwind CSS, Lucide React.
- **Backend/Database**: Supabase (PostgreSQL).
- **Authentication**: Supabase Auth (Email/Password).
- **Real-time**: Supabase Realtime (WebSockets) for instant UI updates.

## 🚦 Getting Started

### Prerequisites
- Node.js (v18+)
- Bun or NPM

### Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd PROJECT
   ```

2. **Frontend Configuration**
   - Navigate to `PROJECT/frontend`.
   - Create a `.env.local` file with your Supabase credentials:
     ```env
     NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
     NEXT_PUBLIC_SUPABASE_ANON_KEY=your_anon_key
     ```

3. **Install Dependencies**
   ```bash
   cd PROJECT/frontend
   npm install
   ```

4. **Run Development Server**
   ```bash
   npm run dev
   ```

## 🏗 Database Schema

The system uses the following core tables in Supabase:
- `profiles`: User roles and personal info.
- `rooms` & `beds`: Infrastructure mapping.
- `students`: Enrollment and bed assignments.
- `complaints`: Issue tracking.
- `notices`: Communication board.
- `rent`: Financial records.

## 🔄 Real-time Integration

The app uses `supabase.channel()` to subscribe to database changes. Any update to rooms, complaints, or notices in the database is automatically broadcasted to all active users without a page refresh.
