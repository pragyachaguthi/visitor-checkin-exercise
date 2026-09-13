# Regression Subset – Visitor Registration Form Update

This subset focuses on **form input validation** after a minor update to the registration form.  
Each test case is either **included** (to be re-run) or **excluded** (safe to skip), with rationale provided.

---

## Included Test Cases

- **TC-01 Verify visitor registration with valid details**  
  *Rationale:* Ensures the form still accepts complete valid input after update.

- **TC-02 Verify registration with only mandatory fields**  
  *Rationale:* Confirms optional fields remain optional.

- **TC-11 Verify submission with empty Full Name**  
  *Rationale:* Validates required field enforcement.

- **TC-12 Verify submission without selecting Host**  
  *Rationale:* Validates required field enforcement.

- **TC-13 Verify whitespace as Full Name**  
  *Rationale:* Ensures invalid whitespace-only input is rejected.

- **TC-14 Verify very long Full Name input**  
  *Rationale:* Confirms length validation is enforced.

- **TC-15 Verify special characters in Full Name**  
  *Rationale:* Ensures invalid characters are blocked.

- **TC-16 Verify numeric value in Full Name**  
  *Rationale:* Ensures numeric-only input is rejected.

---

## Excluded Test Cases

- **TC-03, TC-17 (Company field)**  
  *Rationale:* Company field unchanged; not impacted by form update.

- **TC-04, TC-18 (Purpose field)**  
  *Rationale:* Purpose field unchanged; not impacted by form update.

- **TC-05, TC-06, TC-19 (Host dropdown behavior)**  
  *Rationale:* Dropdown logic not part of form field validation update.

- **TC-07–TC-10 (Visitor list, check-in time, timezone)**  
  *Rationale:* Display logic, not input validation.

- **TC-20–TC-25 (Checkout/deactivation)**  
  *Rationale:* Post-registration workflows unaffected by form input changes.

- **TC-26–TC-29 (Pagination)**  
  *Rationale:* List navigation unaffected by form input changes.

 - **TC‑26 (Duplicate registration)** 
   Rationale: Duplicate handling not impacted by form input validation update.

---

## Summary

This regression subset ensures that **critical input validation paths** (required fields, whitespace, length, character restrictions) are tested after the update.  
Other areas (lists, pagination, checkout) are excluded because they are downstream features not directly impacted by the form update.
