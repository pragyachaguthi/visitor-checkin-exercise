# Visitor Check-In Feature – QA Suite

---

## Happy Path

### TC-01 Verify visitor registration with valid details
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name, Company, Host, and Purpose are entered.
  2. Confirm Submit is clicked.
- Expected Result: Visitor is registered successfully and appears in Active Visitors.
- Actual Result: Visitor registered successfully and appears in Active Visitors.
- Status: [pass]

### TC-02 Verify registration with only mandatory fields
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name and Host are entered.
  2. Confirm Company and Purpose are left blank.
  3. Confirm Submit is clicked.
- Expected Result: Visitor is registered successfully if optional fields are allowed.
- Actual Result: Visitor registered successfully with only mandatory fields.
- Status: [pass]

### TC-03 Verify valid Company entry
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm valid Company name is entered.
  2. Confirm Submit is clicked.
- Expected Result: Company name is displayed correctly in Active Visitors.
- Actual Result: Company name displayed correctly.
- Status: [pass]

### TC-04 Verify valid Purpose entry
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm valid Purpose is entered.
  2. Confirm Submit is clicked.
- Expected Result: Purpose is displayed correctly in Active Visitors.
- Actual Result: Purpose displayed correctly.
- Status: [pass]

### TC-05 Verify Host dropdown displays available hosts
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Host dropdown is opened.
- Expected Result: Active/selectable employees are displayed.
- Actual Result: Host dropdown displayed available hosts.
- Status: [pass]

### TC-06 Verify host selection
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm a host is selected from dropdown.
- Expected Result: Selected host is displayed in the field.
- Actual Result: Host selection displayed correctly.
- Status: [pass]

### TC-07 Verify newly registered visitor appears in list
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm valid visitor registration.
  2. Confirm Active Visitors list is refreshed.
- Expected Result: Visitor appears in Active Visitors list.
- Actual Result: Visitor appeared in Active Visitors list.
- Status: [pass]

### TC-08 Verify visitor details
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm visitor is registered with known details.
- Expected Result: Name, Company, Host, and Purpose match entered data.
- Actual Result: Visitor details matched entered data.
- Status: [pass]

### TC-09 Verify check-in time display
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm visitor registration.
- Expected Result: Check-in time is displayed for visitor.
- Actual Result: Check-in time is displayed for visitor.
- Status: [pass]

### TC-10 Verify local timezone
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm visitor registration.
  2. Confirm displayed time matches receptionist’s local time.
- Expected Result: Time is displayed in receptionist’s local timezone.
- Actual Result: Time not matching with KTM timezone.
- Status: [pass]

---

## Negative Cases

### TC-11 Verify submission with empty Full Name
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name is left blank.
  2. Confirm Host is selected.
  3. Confirm Submit is clicked.
- Expected Result: Validation message is displayed; visitor is not registered.
- Actual Result: Validation message displayed, visitor not registered.
- Status: [pass]

### TC-12 Verify submission without selecting Host
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name is entered.
  2. Confirm Host is left as default “Select host…”.
  3. Confirm Submit is clicked.
- Expected Result: Validation message is displayed; visitor is not registered.
- Actual Result: Validation message displayed; visitor not registered.
- Status: [pass]

### TC-13 Verify whitespace as Full Name
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm spaces are entered in Full Name.
  2. Confirm Submit is clicked.
- Expected Result: System rejects input and displays validation.
- Actual Result: Registration successful with whitespace input.
- Status: [fail]

### TC-14 Verify very long Full Name input
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name exceeds allowed length.
  2. Confirm Submit is clicked.
- Expected Result: System restricts or validates input appropriately.
- Actual Result: System allowed very long names.
- Status: [fail]

### TC-15 Verify special characters in Full Name
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm special characters are entered in Full Name.
  2. Confirm Submit is clicked.
- Expected Result: System rejects invalid characters.
- Actual Result: System allowed special characters.
- Status: [fail]

### TC-16 Verify numeric value in Full Name
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm numeric value is entered in Full Name.
  2. Confirm Submit is clicked.
- Expected Result: System rejects numeric input.
- Actual Result: System allowed numeric input.
- Status: [fail]

### TC-17 Verify special characters in Company
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Company name entered as “ABC & Co.”.
  2. Confirm Submit is clicked.
- Expected Result: System accepts valid special characters if supported.
- Actual Result: System accepted special characters.
- Status: [pass]

### TC-18 Verify Purpose field left empty
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Purpose field is left blank.
  2. Confirm Submit is clicked.
- Expected Result: Visitor is registered if Purpose is optional.
- Actual Result: Visitor registered successfully without Purpose.
- Status: [pass]

### TC-19 Verify deactivated host is not selectable
- Preconditions: Host is deactivated.
- Steps:
  1. Confirm Host dropdown is opened.
- Expected Result: Deactivated employee is not available.
- Actual Result: No access to deactivate hosts.
- Status: [blocked]

### TC-20 Verify check-out of active visitor
- Preconditions: Visitor is active.
- Steps:
  1. Confirm Check Out is clicked for visitor.
- Expected Result: Visitor is removed from Active Visitors.
- Actual Result: Visitor removed successfully.
- Status: [pass]

### TC-21 Verify checked-out visitor is no longer active
- Preconditions: Visitor is checked out.
- Steps:
  1. Confirm page is refreshed.
- Expected Result: Visitor does not appear in Active Visitors.
- Actual Result: Visitor not appearing after checkout.
- Status: [pass]

### TC-22 Verify correct visitor is checked out
- Preconditions: Multiple visitors are active.
- Steps:
  1. Confirm Check Out is clicked for one visitor.
- Expected Result: Only selected visitor is checked out.
- Actual Result: Correct visitor checked out.
- Status: [pass]

### TC-23 Verify repeat registration after checkout
- Preconditions: Visitor is checked out.
- Steps:
  1. Confirm visitor is registered again.
- Expected Result: Visitor is allowed to register again.
- Actual Result: Visitor registered again successfully.
- Status: [pass]

### TC-24 Verify deactivated visitor not shown in active list
- Preconditions: Visitor record is deactivated.
- Steps:
  1. Confirm Active Visitors list is refreshed.
- Expected Result: Deactivated visitor doesnotappear.
- Actual Result:  deactivated visitors still appears.
- Status: [fail]

### TC-25 Verify deactivated visitor cannot be registered for repeat visit
- Preconditions: Visitor record is deactivated.
- Steps:
  1. Confirm attempt to register deactivated visitor.
- Expected Result: Visitor is not available for repeat visit.
- Actual Result: Deactivated visitors can be registered again.
- Status: [fail]

### TC-26 Verify duplicate registration
- Preconditions: Visitor is registered
- Steps:
  1. register visitor with identical information as registered visitor
- Expected Result: dublication resistration not allowed
- Actual Result: Visitor registered successfully.
- Status: [fail]



---

## Boundary & Pagination Cases

### TC-27 Verify active list pagination
- Preconditions: More than 20 visitors registered.
- Steps:
  1. Confirm 21 visitors are registered.
  2. Confirm Active Visitors list is displayed.
- Expected Result: Only 20 records appear per page.
- Actual Result: Pagination worked correctly.
- Status: [pass]

### TC-28 Verify navigation to next page
- Preconditions: More than 20 visitors registered.
- Steps:
  1. Confirm Next button is clicked.
- Expected Result: Remaining visitors are displayed on next page.
- Actual Result: Next button worked correctly.
- Status: [pass]

### TC-29 Verify navigation to previous page
- Preconditions: More than 20 visitors registered, currently on page 2.
- Steps:
  1. Confirm Previous button is clicked.
- Expected Result: Page 1 is displayed.
- Actual Result: Previous button worked correctly.
- Status: [pass]

### TC-30 Verify Next button disabled on last page
- Preconditions: Navigate to last page of visitors.
- Steps:
    1. click next button
- Expected Result: next button deactivated.
- Actual Result: next button deactivated.
- Status: [fail]


## TC-31 Verify Next button remains enabled after multiple checkouts
Preconditions: 
- Active Visitors list contains multiple pages of entries.  
Steps:  
  1. Navigate to the Active Visitors list.  
  2. Go to  any page that is not the last.  
  3. Select multiple visitors and click “Check Out” for each.  
  4. Observe the pagination controls after checkout.  
- Expected Result: The “Next” button remains enabled if subsequent pages still contain active visitors.  
- Actual Result: The “Next” button becomes disabled, preventing navigation forward.  
 Status:  [fail]
