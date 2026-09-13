# Defect Report

## Defect 1
**Summary:** Missing checkout success message  
**Type:** Usability  
**Description:** When a receptionist checks out a visitor, no confirmation message is displayed. This leaves the user uncertain whether the action succeeded.  
**Steps to Reproduce:**  
1. Log in as receptionist.  
2. Register a visitor.  
3. Click "Check Out" on the visitor.  
**Expected Result:** A success message such as "Checkout successful" should appear.  
**Actual Result:** No message is displayed; only the table updates silently.  

---

## Defect 2
**Summary:** Missing registration success message  
**Type:** Usability  
**Description:** After registering a visitor, no confirmation message is shown. Receptionists may be unsure if the registration was successful.  
**Steps to Reproduce:**  
1. Log in as receptionist.  
2. Fill in visitor details and submit registration.  
**Expected Result:** A success message such as "Registration successful" should appear.  
**Actual Result:** No message is displayed; only the table updates silently.  

---

## Defect 3
**Summary:** Full Name field accepts invalid input  
**Type:** Data Validation  
**Description:** The Full Name field accepts excessively long names, whitespace-only input, numbers, and special characters.  
**Steps to Reproduce:**  
1. Attempt to register a visitor with invalid input (e.g., "1234!!!" or long strings).  
**Expected Result:** Input should be restricted to valid alphabetic names with reasonable length.  
**Actual Result:** Invalid input is accepted and registration proceeds.  

---

## Defect 4
**Summary:** Company Name field accepts invalid input  
**Type:** Data Validation  
**Description:** The Company Name field accepts excessively long names, whitespace-only input, numbers, and special characters.  
**Steps to Reproduce:**  
1. Attempt to register a visitor with invalid company name (e.g., "%%%%" or long strings).  
**Expected Result:** Input should be restricted to valid company names with reasonable length.  
**Actual Result:** Invalid input is accepted and registration proceeds.  

---

## Defect 5
**Summary:** Duplicate visitor registration allowed  
**Type:** Functional  
**Description:** The system allows registering the same visitor multiple times without restriction.  
**Steps to Reproduce:**  
1. Register a visitor with valid details.  
2. Register the same visitor again with identical details.  
**Expected Result:** System should prevent duplicate registrations or prompt the receptionist.  
**Actual Result:** Duplicate entries are created in the active visitor list.  

---

## Defect 6
**Summary:** Time zone mismatch  
**Type:** Data  
**Description:** The check-in time displayed does not match the receptionist’s local timezone (KTM).  
**Steps to Reproduce:**  
1. Register a visitor.  
2. Observe the check-in time displayed in the active visitor list.  
**Expected Result:** Time should match the receptionist’s local timezone.  
**Actual Result:** Time displayed does not align with KTM timezone.  

---

## Defect 7
**Summary:** Inconsistent required field validation  
**Type:** Functional  
**Description:** Both Full Name and Host fields are marked required, but when submitting with both empty, only the Full Name field shows the "Please fill out this form" message.  
**Steps to Reproduce:**  
1. Attempt to register a visitor with both Full Name and Host empty.  
**Expected Result:** Both fields should display required field validation messages.  
**Actual Result:** Only Full Name shows the validation message; Host does not.  

---

## Defect 8
**Summary:** Deactivation not restricted to administrators  
**Type:** Security/Functional  
**Description:** Receptionists can access deactivation functionality, which should be restricted to administrators.  
**Steps to Reproduce:**  
1. Log in as receptionist.
2. check the available routes with "rails routes " command. you will see decativation route.  
3. Using Postman, send a PATCH request:  
PATCH http://localhost:3000/api/visitors/<id>/deactivate
4. Observe the response.  
**Expected Result:** Only administrators should be able to call the deactivation API. Receptionists should receive a "Forbidden" error.  
**Actual Result:** Receptionists can successfully deactivate visitors via the API.  

---

## Defect 9
**Summary:** Deactivated visitors still appear in active list  
**Type:** Functional  
**Description:** After deactivation, visitors continue to appear in the active visitor list.  
**Steps to Reproduce:**  
1. Using Postman, send a PATCH request:  
PATCH http://localhost:3000/api/visitors/<id>/deactivate

→ Response shows `"active": false`.  
2. Fetch the active visitor list:  
GET http://localhost:3000/api/visitors?page=1

3. Check if the deactivated visitor still appears.  
**Expected Result:** Deactivated visitors should be excluded from the active list.  
**Actual Result:** Deactivated visitors remain visible in the active list despite `"active": false`.  
