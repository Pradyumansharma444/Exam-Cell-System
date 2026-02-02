# Requirements Document - ExamCell System

## Project Objective

To provide a fully automated, data-driven platform for managing student records, exam results, ATKT (backlog) applications, and institutional communications.

## Core Functional Requirements

1. **Student Master**: Centralized source of truth for student contact details (Email, Phone) linked by Roll Number.
2. **Automated ATKT Management**:
   - Auto-detection of failing students from result uploads.
   - Automatic creation of "NOT_APPLIED" backlog records.
   - Secure payment gateway (Razorpay) for application submission.
   - Auto-generation of Hall Tickets upon payment.
3. **Data-Driven Messaging Engine**:
   - **Zero Manual Input**: Notifications trigger automatically based on data changes.
   - **KT Alerts**: Triggered immediately when a 'FAIL' result is detected.
   - **Fee Reminders**: Triggered when a student's status is set to 'PENDING'.
   - **Schedule Broadcasts**: Notifies relevant departments when an exam form opens.
4. **Duplicate Prevention**: System must verify `notification_logs` before sending to avoid spam.
5. **Admin Dashboard**: Bulk student management (Upload/Export), Result processing, and Automation tracking.

## Non-Functional Requirements

- **Reliability**: Use Roll Number as the consistent Primary Key across all modules.
- **Security**: Protect sensitive API keys (Twilio, Resend, Razorpay) via environment variables.
- **Scalability**: Handle bulk uploads of thousands of results/students efficiently.
