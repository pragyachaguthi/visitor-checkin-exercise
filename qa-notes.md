# QA Notes – Visitor Check-In Feature

## Highest-Risk Areas
# The **Full Name and company field validation** is the highest-risk area.  
**Reasoning:**  
- Multiple failures were observed (whitespace-only input accepted, very long names allowed, special characters and numeric input not rejected).  
- This field is mandatory and central to visitor identification.  
- Weak validation here can lead to corrupted records, duplicate entries, or compliance/security issues.  
- Since the registration form update directly affects input handling, this area is most likely to break and requires strict regression coverage.


 # The deactivation security defect  is the highest-risk area.  
**Reasoning:**  
- Receptionists are currently able to access deactivation functionality, which should be restricted to administrators.  
- This is a **security/authorization flaw** that breaks role-based access control.  
- Unlike validation or display bugs, this exposes unauthorized capabilities and could lead to compliance, audit, or data integrity issues.  
- Because security defects carry greater risk than usability or functional issues, this must be resolved before sign-off.





## Question for Product Owner
 Should **deactivation functionality always be restricted to administrator roles**, or are there scenarios where receptionists should have limited deactivation rights?  
Clarifying this ensures QA can align test cases with the intended access control model and compliance requirements.
