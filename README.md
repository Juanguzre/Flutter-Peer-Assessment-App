# Application Proposal

## Author

Juan Pablo Guzman Restrepo.

## Project

Mobile Development Project — Peer Assessment App

---

## 1. General Description

**Peer Assessment App** is a mobile application that will be developed in Flutter and will allow the evaluation of students' performance and commitment in collaborative activities within university courses.

The system will facilitate peer assessment in group work by providing tools to manage courses, groups, assessment activities, and result analysis. The application promotes individual responsibility, transparency in collaborative work, and the monitoring of academic performance.

---

## 2. Analyzed References

### Google Classroom

* Course and student management.
* Clear organization of academic activities.
* Simple and intuitive teacher–student interaction flow.

### Moodle

* Structured assessment system.
* Advanced user and role management.
* Detailed performance tracking.

### Peergrade / Peer Assessment Systems

* Structured peer assessment.
* Feedback among students.
* Visualization of results and metrics.

---

## 3. Architecture and Solution Design

### Proposed architecture

The application follows **Clean Architecture** principles to ensure scalability, maintainability, and separation of responsibilities.

**System layers:**

* Presentation Layer: user interface and interaction handling.
* Domain Layer: business logic and system rules.
* Data Layer: external services, storage, and persistence.

### State management

* GetX for state management, navigation, and dependencies.

### System configuration

* Single application with role support.
* Secure authentication.
* Remote data storage.
* Group import from an external platform.

---

## 4. Main Features

### Teacher

* Create and manage courses.
* Invite students through private access or verification.
* Import groups from an external system.
* Create assessment activities.
* Define result visibility (public or private).
* View performance metrics.
* Review detailed results by student and group.

### Student

* Join courses.
* View work group.
* Evaluate classmates (no self-assessment).
* Review assessment results.
* Check activity history.

---

## 5. Evaluation Criteria

Each student is evaluated according to the following criteria:

* Punctuality
* Contributions
* Commitment
* Attitude

### Evaluation scale

| Level | Description       |
| ----- | ----------------- |
| 2.0   | Needs Improvement |
| 3.0   | Adequate          |
| 4.0   | Good              |
| 5.0   | Excellent         |

Self-assessment is not allowed.

---

## 6. System Functional Flow

### General system flow

1. The teacher creates a course.
2. The teacher invites students to the course.
3. The system imports the groups from the external platform.
4. The teacher creates an assessment activity.
5. The teacher defines the duration and visibility of the assessment.
6. Students access the active assessment.
7. Each student evaluates their group members.
8. The system stores and processes the grades.
9. The system calculates averages by activity, group, and student.
10. The results are displayed according to the visibility settings.
11. The teacher analyzes metrics and performance.

### General system flow diagram

```mermaid
flowchart TD
    A[Teacher Creates Course] --> B[Teacher Invites Students]
    B --> C[System Imports Groups]
    C --> D[Teacher Creates Assessment]
    D --> E[Teacher Defines Duration and Visibility]
    E --> F[Students Access Active Assessment]
    F --> G[Students Evaluate Group Members]
    G --> H[System Stores and Processes Grades]
    H --> I[System Calculates Averages]
    I --> J[Results Displayed According to Visibility]
    J --> K[Teacher Reviews Metrics and Performance]
```

---

### Peer assessment flow (student)

```mermaid
flowchart TD
    A[Student Login] --> B[Open Active Course]
    B --> C[Select Active Assessment]
    C --> D[View Group Members]
    D --> E[Select Teammate]
    E --> F[Evaluate Punctuality]
    F --> G[Evaluate Contributions]
    G --> H[Evaluate Commitment]
    H --> I[Evaluate Attitude]
    I --> J[Submit Evaluation]
    J --> K[System Stores Results]
    K --> L{More Teammates?}
    L -->|Yes| E
    L -->|No| M[Assessment Completed]
```

1. The student logs in.

<img width="507" height="898" alt="image" src="https://github.com/user-attachments/assets/674fcb14-a8ba-42ee-a173-08bcb3eb3983" />

2. Selects the active course.

<img width="499" height="899" alt="image" src="https://github.com/user-attachments/assets/21901d05-a83a-4487-827c-69fea8fa2c79" />

3. Selects a group member.

<img width="492" height="899" alt="image" src="https://github.com/user-attachments/assets/cb820d62-0c81-452f-b1ec-b96ea87c5dc9" />

5. Evaluates the criteria:

   * Punctuality

<img width="512" height="899" alt="image" src="https://github.com/user-attachments/assets/d417bc45-7821-479f-a1f0-d2e96fc1196b" />

* Contributions

<img width="504" height="901" alt="image" src="https://github.com/user-attachments/assets/d7686622-d254-4f6c-9bd1-168fb0b299c7" />

* Commitment

<img width="513" height="900" alt="image" src="https://github.com/user-attachments/assets/394847d8-687d-4b28-9fb1-2e67787e6543" />

* Attitude

<img width="509" height="901" alt="image" src="https://github.com/user-attachments/assets/7d2aa526-b401-43f4-a74e-444fc254172d" />

6. The system records the results.

<img width="504" height="896" alt="image" src="https://github.com/user-attachments/assets/21160c85-d90d-4d44-b2f1-bd09ba69a29c" />

---

### Assessment creation flow (teacher)

```mermaid
flowchart TD
    A[Teacher Login] --> B[Open Course]
    B --> C[Select Create Assessment]
    C --> D[Enter Assessment Name]
    D --> E[Define Duration]
    E --> F[Define Visibility]
    F --> G[Select Criteria]
    G --> H[Publish Assessment]
    H --> I[System Activates Assessment]
```

1. The teacher logs in.

<img width="486" height="896" alt="image" src="https://github.com/user-attachments/assets/827bfa61-78ec-4e4a-887f-91bd7319e6b0" />

2. Selects a course.

<img width="508" height="898" alt="image" src="https://github.com/user-attachments/assets/718d7cdd-2f62-46df-98f2-916efd443c14" />

3. Defines:

   * name

<img width="508" height="902" alt="image" src="https://github.com/user-attachments/assets/78d013c0-54f0-4e92-8404-49a9d42191e3" />

* duration

<img width="509" height="902" alt="image" src="https://github.com/user-attachments/assets/511cfa49-99b7-482a-bdd3-8534b193da3d" />

* visibility

<img width="511" height="901" alt="image" src="https://github.com/user-attachments/assets/dcc7eb73-b2af-4780-aee5-e7c494dcb902" />

* criteria

<img width="511" height="901" alt="image" src="https://github.com/user-attachments/assets/251121f5-98ac-4022-9ae4-fa47c3f60a75" />

4. Publishes the assessment.

<img width="501" height="899" alt="image" src="https://github.com/user-attachments/assets/b2ef4757-ed78-469a-9377-8711e95b7c4f" />

---

### Results visualization flow

```mermaid
flowchart TD
    A[Assessment Ends] --> B[System Collects Peer Evaluations]
    B --> C[Validate Data]
    C --> D[Calculate Student Averages]
    D --> E[Calculate Group Averages]
    E --> F[Calculate Activity Averages]
    F --> G[Generate Metrics and Analytics]
    G --> H[Store Results]
    H --> I{Visibility Type}
    I -->|Teacher Only| J[Only Teacher Can View Results]
    I -->|Teacher and Students| K[Teacher and Students Can View Results]
```

1. The system processes the assessments.
2. Calculates averages.

<img width="504" height="900" alt="image" src="https://github.com/user-attachments/assets/f7e74425-430e-4454-af30-b116de6fc9d7" />

5. Generates metrics:

   * average by group

<img width="513" height="903" alt="image" src="https://github.com/user-attachments/assets/508ab0cf-c2e9-4caa-ba4a-6526bb604834" />

* comparison between groups through charts

<img width="493" height="904" alt="image" src="https://github.com/user-attachments/assets/cf0a1edf-b6fc-43a5-90e3-1e92384e9a21" />

* Work completion

<img width="506" height="906" alt="image" src="https://github.com/user-attachments/assets/51daccbf-eee9-417f-aa7f-920ec7cbf486" />

* Performance trends

<img width="527" height="904" alt="image" src="https://github.com/user-attachments/assets/245a6227-5a58-4ec7-b7f0-deb49c00b1b1" />

5. Displays results according to the configuration:

   * teacher only

<img width="516" height="901" alt="image" src="https://github.com/user-attachments/assets/c10b7484-e426-40ac-afef-e85817fa7e5c" />

* teacher and students

<img width="511" height="895" alt="image" src="https://github.com/user-attachments/assets/4a380bfd-fcce-4eef-9cc0-7045cd4a4d80" />

---

## 7. UX/UI Design

The application design prioritizes:

* Usability and visual clarity.
* Intuitive navigation.
* Immediate user feedback.
* Clear visualization of metrics.
* Role-based adaptable interface.
* Accessibility and visual consistency.

The system includes:

* Authentication screens.
* User dashboard.
* Guided assessment flow.
* Course management.
* Results and analytics panel.

### Authentication flow

```mermaid
flowchart TD
    A[Open App] --> B[Login Screen]
    B --> C[Enter Credentials]
    C --> D{Credentials Valid?}
    D -->|Yes| E[Access Granted]
    E --> F{User Role}
    F -->|Teacher| G[Teacher Dashboard]
    F -->|Student| H[Student Dashboard]
    D -->|No| I[Show Error Message]
    I --> B
```

### Dashboard flow

```mermaid
flowchart TD
    A[Login] --> B{User Role}
    B -->|Teacher| C[Teacher Dashboard]
    C --> D[View Courses]
    D --> E[View Active Assessments]
    E --> F[View Pending Actions]
    F --> G[View Performance Summaries]

    B -->|Student| H[Student Dashboard]
    H --> I[View Joined Courses]
    I --> J[View Active Assessments]
    J --> K[View Pending Evaluations]
    K --> L[View Recent Results and History]
```

---

## 8. Proposal Justification

* Improves individual responsibility.
* Enables objective evaluation of teamwork.
* Facilitates academic performance analysis.
* Reduces bias in group assessments.
* Provides quantifiable feedback.

---

## 9. Figma Prototype

Prototype link:
[https://www.figma.com/make/fUff3akO7fkAHo6xS4PnOS/Peer-Assessment-App-UI-UX?t=na7wTLLx4yijH20F-1](https://www.figma.com/make/fUff3akO7fkAHo6xS4PnOS/Peer-Assessment-App-UI-UX?t=na7wTLLx4yijH20F-1)

The prototype includes:

* Authentication flow.
* User dashboard.
* Peer assessment.
* Course management.
* Results panel.

---

## 10. Technologies

* Flutter
* GetX
* Clean Architecture
* Authentication and remote storage services

---

## 11. Additional User Flows

### Teacher flow — Create and manage course

```mermaid
flowchart TD
    A[Teacher Login] --> B[Teacher Dashboard]
    B --> C[Select Create Course]
    C --> D[Enter Course Information]
    D --> E[Confirm Creation]
    E --> F[System Stores Course]
    F --> G[Course Management View]
    G --> H[Edit Course]
    G --> I[Invite Students]
    G --> J[Import Groups]
    G --> K[Create Assessment]
    G --> L[View Results and Metrics]
```

### Teacher flow — Invite students

```mermaid
flowchart TD
    A[Open Course] --> B[Select Invite Students]
    B --> C{Choose Invitation Method}
    C -->|Private Code| D[Generate Access Code]
    C -->|Verification| E[Enable Verification Access]
    D --> F[Students Use Invitation]
    E --> F
    F --> G[System Enrolls Students]
    G --> H[Teacher Reviews Enrolled Students]
```

### Teacher flow — Import groups

```mermaid
flowchart TD
    A[Open Course] --> B[Select Import Groups]
    B --> C[Connect External Platform]
    C --> D[Retrieve Group Data]
    D --> E[Review Imported Groups]
    E --> F[Confirm Import]
    F --> G[System Stores Groups]
    G --> H[Students Assigned to Groups]
```

### Student flow — Join course

```mermaid
flowchart TD
    A[Student Login] --> B[Student Dashboard]
    B --> C[Select Join Course]
    C --> D[Enter Code or Verification Data]
    D --> E{Access Valid?}
    E -->|Yes| F[Student Added to Course]
    F --> G[Course Appears on Dashboard]
    E -->|No| H[Show Error Message]
    H --> C
```

### Rule flow — No self-assessment

```mermaid
flowchart TD
    A[Student Opens Assessment] --> B[System Loads Group Members]
    B --> C{Is Selected User the Same Student?}
    C -->|Yes| D[Block Action]
    D --> E[Show Warning Message]
    C -->|No| F[Allow Evaluation]
```

### Student flow — View results

```mermaid
flowchart TD
    A[Student Login] --> B[Open Course]
    B --> C[Select Completed Assessment]
    C --> D{Visibility Allows Access?}
    D -->|Yes| E[Display Results]
    D -->|No| F[Show Restricted Access Message]
```

### Activity history flow

```mermaid
flowchart TD
    A[User Login] --> B{User Role}
    B -->|Student| C[Open Activity History]
    C --> D[View Completed Assessments]
    D --> E[View Pending Assessments]
    E --> F[View Past Results]
    B -->|Teacher| G[Open Assessment History]
    G --> H[View Created Assessments]
    H --> I[View Assessment Status]
```

Un detalle: en tu numeración original hay un par de saltos, por ejemplo aparece el paso 5 después del 3 en algunos flujos. Lo dejé igual en varias partes para no alterar demasiado tu estructura visual. Si quieres, te lo corrijo para que quede completamente pulido y listo para entrega.

* Clean Architecture
