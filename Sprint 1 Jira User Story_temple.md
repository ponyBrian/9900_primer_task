# Sprint 1 Jira User Stories - Template for H16C_ALMOND

---

### PROJ-01: SLP Login

**As a** Speech Language Pathologist  
**I want** to securely log in  
**So that** I can access my assigned patients.

**Acceptance Criteria:**
- Login form accepts email and password.
- Secure authentication (JWT token issued on success).
- Error message displayed on invalid credentials.
- Session timeout after inactivity.

**Story Points**: 3  
**Priority**: High

---

### PROJ-02: View Assigned Children List

**As a** SLP  
**I want** to view all assigned children  
**So that** I can select which child to monitor.

**Acceptance Criteria:**
- List shows Child ID, Name, Age, Level, Last Updated.
- Clicking child navigates to child profile view.

**Story Points**: 3  
**Priority**: High

---

### PROJ-03: Add/Edit Child Profiles

**As a** SLP  
**I want** to create and edit child profiles  
**So that** patient information stays accurate.

**Acceptance Criteria:**
- Add new child with Name, DOB, Level, Assigned SLP.
- Edit existing child profile.
- Delete child if necessary.

**Story Points**: 5  
**Priority**: High

---

### PROJ-04: Create Exercises

**As a** SLP  
**I want** to create exercises by selecting words  
**So that** I can assign personalized tasks to children.

**Acceptance Criteria:**
- Display word list from Firebase data.
- Select multiple words to build exercise.
- Save exercise into database.

**Story Points**: 5  
**Priority**: Medium

---

### PROJ-05: Assign Exercise to Child

**As a** SLP  
**I want** to assign exercises to children  
**So that** I can track their training assignments.

**Acceptance Criteria:**
- Assign created exercise to child.
- Mark as Initial Assessment if applicable.
- Store assigned date & status (pending, in-progress, completed).

**Story Points**: 5  
**Priority**: Medium

---

### Total Sprint 1 Estimated Story Points: 21
(⚠ Ideally, keep Sprint 1 total ≤ ⅓ of full backlog story points)

---

✅ You can directly copy this into your Jira issues as **Story type tickets**.
