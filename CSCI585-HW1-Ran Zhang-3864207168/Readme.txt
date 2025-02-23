README - Dental Practice ER Diagram  

📌 Course: CSCI 585  
📌 Assignment: HW1 
📌 Author: Ran Zhang  
📌 ID: 3864207168

---

## **1️⃣ Project Overview**  
Based on the HW1 assignment description, my task is to design a **conceptual ER diagram** for a newly established dental practice to support its daily operations.  

I designed this database to focus on the following key areas:  
- 🏥 **Patient Management**  
- 📄 **Billing & Insurance Processing**  
- 💊 **Treatment & Medical Records**  
- 📅 **Appointment Scheduling**  
- 💰 **Financial Tracking & Payroll Management**  

---

## **2️⃣ ER Diagram Tools & Implementation**  
I used **draw.io** to create the ER diagram and applied **Crow’s Foot Notation** for modeling.  

---

## **3️⃣ Design Choices & Assumptions**  
I made the following design choices and assumptions to optimize the operations of this dental practice and ensure clear entity relationships:  

### **🔹 Core Entities & Relationships**  

#### **👤 Patient Management**  
- A **Patient** can have **one or more Appointments** (1:M) to schedule visits.  
- A **Patient** may undergo **one or more Treatments** (1:M) recorded in their medical history.  
- A **Patient** can have **one or more Billing records** (1:M) to track payments and insurance claims.  

#### **🩺 Doctor & Staff Structure**  
- Each **Doctor** is also an **Employee (Staff)** (`Doctor` inherits from `Staff`) (1:1).  
- A **Doctor** can perform **one or more Treatments** (1:M) for patients.  
- A **Doctor** can be assigned to **one or more Appointments** (1:M) to manage patient visits.  

#### **📅 Appointment Scheduling**  
- Each **Appointment** is linked to **one Patient and one Doctor** (1:1) to ensure proper scheduling.  
- An **Appointment** may involve **one or more Treatments** (1:M), documenting all procedures conducted during the visit.  

#### **💰 Billing & Financial Management**  
- A **Billing** record is linked to **one Patient** (1:M) for tracking financial transactions.  
- A **Billing** record may include **one or more Treatments** (M:N), managed via the `Billing-Detail` bridge entity.  
- Each **Billing** record can generate **one or more Income records** (1:M), distinguishing between **Patient payments and Insurance coverage**.  
- The `Expense` entity records operational costs, such as **staff salaries, rent, and dental supplies**.  

#### **🛡️ Insurance Management**  
- A **Patient** can have **one or more Insurance Providers** (M:N) to cover medical expenses.  
- `Patient-Insurance` serves as a bridge entity managing the **Patient-Insurance Provider** relationship.  

#### **📊 Staff Payroll**  
- All employees, including **Doctors**, are stored in the `Staff` entity for **consistent HR management**.  
- `Expense` records with `Staff_ID` track **salary payments** for employees.  

---

## **4️⃣ Key Features & Design Strengths**  
I believe my design is well-structured in terms of **financial management and clinic operations**. I designed **Billing, Income, and Expense as separate entities**, which I think makes financial data more transparent. Additionally, I introduced `Billing-Detail` and `Patient-Insurance` as bridge entities, which I believe makes relationships clearer and helps avoid data redundancy.  

