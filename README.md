# 📚 Smart Library Request Workflow in ServiceNow

## 📌 Project Overview

The **Smart Library Request Workflow in ServiceNow** is a custom ServiceNow application developed to automate and simplify library book management. The application enables students to request books online while allowing librarians to manage the book catalog, approve or reject requests, and automatically update book availability through workflow automation.

The project demonstrates ServiceNow platform capabilities including custom tables, role-based access control (ACLs), Flow Designer, UI Policies, Reports, and workflow automation.

---

## 🎯 Business Objectives

- Reduce manual library management processes.
- Improve accuracy in tracking library books.
- Automate borrow request approvals.
- Maintain real-time book availability.
- Provide role-based access for students and librarians.
- Generate reports for library usage analysis.

---

## ✨ Features

### Student
- View available books.
- Submit borrow requests.
- Track request status.
- View own borrowing history.

### Librarian
- Add new books.
- Update book information.
- Approve or reject borrow requests.
- Manage book availability.
- View reports and analytics.

### Automation
- Automatic approval workflow.
- Automatic book status update.
- Automatic availability update after return.
- UI Policies for read-only fields.
- Access Control using ACLs.

---

# 🏗️ Project Architecture

```
Student
     │
     ▼
Borrow Request
     │
     ▼
Flow Designer
     │
 ┌────┴────┐
 │         │
Approved  Rejected
 │
 ▼
Book Status = Issued
 │
 ▼
Returned
 │
 ▼
Book Status = Available
```

---

# 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| ServiceNow | Application Development |
| Flow Designer | Workflow Automation |
| Access Control (ACL) | Security |
| UI Policies | Form Behavior |
| Reports | Analytics |
| Custom Tables | Data Management |

---

# 📂 Custom Tables

## Book (`u_book`)

| Field | Type |
|--------|------|
| Book ID | String |
| Title | String |
| Author | String |
| Category | Choice |
| Availability Status | Choice |
| Total Copies | Integer |

---

## Borrow Request (`u_borrow_request`)

| Field | Type |
|--------|------|
| Requested Book | Reference |
| Requested By | Reference |
| Request Date | Date |
| Return Date | Date |
| Status | Choice |

---

# 👥 User Roles

## Student
- Read available books
- Create borrow requests
- View own requests

## Librarian
- Create books
- Update books
- Delete books
- Approve requests
- Reject requests
- Generate reports

---

# 🔄 Workflow

1. Student logs into ServiceNow.
2. Student views available books.
3. Student submits a borrow request.
4. Flow Designer triggers automatically.
5. Librarian reviews the request.
6. If approved:
   - Request status becomes **Approved**
   - Book status changes to **Issued**
7. If rejected:
   - Request status becomes **Rejected**
8. When the book is returned:
   - Request status becomes **Returned**
   - Book status changes back to **Available**

---

# 🔐 Security

Access Control Lists (ACLs) are configured as follows:

## Book Table

| Operation | Student | Librarian |
|-----------|----------|------------|
| Read | ✅ | ✅ |
| Create | ❌ | ✅ |
| Update | ❌ | ✅ |
| Delete | ❌ | ✅ |

## Borrow Request Table

| Operation | Student | Librarian |
|-----------|----------|------------|
| Create | ✅ | ✅ |
| Read | Own Records | All |
| Update | ❌ | ✅ |
| Delete | ❌ | ✅ |

---

# 📊 Reports

The application includes:

- Most Borrowed Books
- Active Borrow Requests
- Borrow Request Status Summary

---

# 🧪 Testing

The application was tested using ServiceNow Impersonation.

### Student Testing

- View books
- Submit request
- Track request

### Librarian Testing

- Add books
- Approve request
- Reject request
- Update status

---

# 📷 Project Screenshots

```
Screenshots/
│
├── Login.png
├── Application.png
├── Roles.png
├── Users.png
├── Book_Table.png
├── Borrow_Request_Table.png
├── Flow_Designer.png
├── ACLs.png
├── Reports.png
├── Testing.png
```

---

# 📁 Repository Structure

```
Smart-Library-Request-Workflow-ServiceNow
│
├── README.md
├── Project_Report.pdf
├── Update_Set.xml
├── Screenshots/
└── Demo_Video_Link.txt
```

---

# 🚀 Future Enhancements

- Email notifications
- Barcode integration
- QR code-based borrowing
- Fine calculation
- Due date reminders
- Dashboard for management
- Mobile support

---

# 👨‍💻 Developer

**Nanda Kishore Reddy Konduru**

GitHub: https://github.com/NandaKishore-04

LinkedIn: https://www.linkedin.com/in/nanda-kishore-reddy-515081294

---

# 📜 License

This project was developed for learning and internship purposes using the ServiceNow Developer Platform.
