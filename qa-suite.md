# Visitor Check-In Feature – QA Suite

---

## Happy Path


### TC-01 verify visitor check in page loads
- Precondition: Application is running
- Steps:
  1. Confirm the application is running.
  2. Check the visitor Check in page.
- Expected Result: visitor checkin page is displayed with register visitor form and active    visitors section.
- Status: [pass]


### TC-02 verify all registration fields are displayed
- precondition: Visitor Checkin page is opened.
- steps: 
  1. Check the Register Visitor form.
  2. Confirm the full name field is displayed.
  3. Confirm the company field is displayed.
  4. Confirm host field is displayed.
  5. Confirm Purpose field is displayed.
  6. Confirm Submit button is displayed.
- expected Result: Full Name , Compant , Host , Purpose fields and Submit button are displayed.
- Status: [pass]


### TC-03 Verify visitor registration with valid details
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name, Company, Host, and Purpose are entered.
  2. Confirm Submit is clicked.
- Expected Result: Visitor is registered successfully and appears in Active Visitors.
- Actual Result: Visitor registered successfully and appears in Active Visitors.
- Status: [pass]

### TC-04 Verify registration with only mandatory fields
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name and Host are entered.
  2. Confirm Company and Purpose are left blank.
  3. Confirm Submit is clicked.
- Expected Result: Visitor is registered successfully if optional fields are allowed.
- Actual Result: Visitor registered successfully with only mandatory fields.
- Status: [pass]

### TC-05 Verify valid Company entry
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm valid Company name is entered.
  2. Confirm Submit is clicked.
- Expected Result: Company name is displayed correctly in Active Visitors.
- Actual Result: Company name displayed correctly.
- Status: [pass]

### TC-06 Verify valid Purpose entry
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm valid Purpose is entered.
  2. Confirm Submit is clicked.
- Expected Result: Purpose is displayed correctly in Active Visitors.
- Actual Result: Purpose displayed correctly.
- Status: [pass]

### TC-07 Verify Host dropdown displays available hosts
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Host dropdown is opened.
- Expected Result: Active/selectable employees are displayed.
- Actual Result: Host dropdown displayed available hosts.
- Status: [pass]

### TC-08 Verify host selection
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm a host is selected from dropdown.
- Expected Result: Selected host is displayed in the field.
- Actual Result: Host selection displayed correctly.
- Status: [pass]

### TC-09 Verify newly registered visitor appears in list
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm valid visitor registration.
  2. Confirm Active Visitors list is refreshed.
- Expected Result: Visitor appears in Active Visitors list.
- Actual Result: Visitor appeared in Active Visitors list.
- Status: [pass]

### TC-10 Verify visitor details
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm visitor is registered with known details.
- Expected Result: Name, Company, Host, and Purpose match entered data.
- Actual Result: Visitor details matched entered data.
- Status: [pass]

### TC-11 Verify check-in time display
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm visitor registration.
- Expected Result: Check-in time is displayed for visitor.
- Actual Result: Check-in time is displayed for visitor.
- Status: [pass]

### TC-12 Verify local timezone
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm visitor registration.
  2. Confirm displayed time matches receptionist’s local time.
- Expected Result: Time is displayed in receptionist’s local timezone.
- Actual Result: Time not matching with KTM timezone and displays UTC time.
- Status: [fail]

---

## Negative Cases

### TC-13 Verify submission with empty Full Name
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name is left blank.
  2. Confirm Host is selected.
  3. Confirm Submit is clicked.
- Expected Result: Validation message is displayed; visitor is not registered.
- Actual Result: Validation message displayed, visitor not registered.
- Status: [pass]

### TC-14 Verify submission without selecting Host
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name is entered.
  2. Confirm Host is left as default “Select host…”.
  3. Confirm Submit is clicked.
- Expected Result: Validation message is displayed; visitor is not registered.
- Actual Result: Validation message displayed; visitor not registered.
- Status: [pass]

### TC-15 Verify whitespace as Full Name
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm spaces are entered in Full Name.
  2. Confirm Submit is clicked.
- Expected Result: System rejects input and displays validation.
- Actual Result: Registration successful with whitespace input.
- Status: [fail]

### TC-16 Verify very long Full Name input
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Full Name exceeds allowed length.
  2. Confirm Submit is clicked.
- Expected Result: System restricts or validates input appropriately.
- Actual Result: System allowed very long names.
- Status: [fail]

### TC-17 Verify special characters in Full Name
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm special characters are entered in Full Name.
  2. Confirm Submit is clicked.
- Expected Result: System rejects invalid characters.
- Actual Result: System allowed special characters.
- Status: [fail]

### TC-18 Verify numeric value in Full Name
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm numeric value is entered in Full Name.
  2. Confirm Submit is clicked.
- Expected Result: System rejects numeric input.
- Actual Result: System allowed numeric input.
- Status: [fail]

### TC-19 Verify special characters in Company
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Company name entered as “ABC & Co.”.
  2. Confirm Submit is clicked.
- Expected Result: System accepts valid special characters if supported.
- Actual Result: System accepted special characters.
- Status: [pass]

### TC-20 Verify Purpose field left empty
- Preconditions: Visitor form is accessible.
- Steps:
  1. Confirm Purpose field is left blank.
  2. Confirm Submit is clicked.
- Expected Result: Visitor is registered if Purpose is optional.
- Actual Result: Visitor registered successfully without Purpose.
- Status: [pass]

### TC-21 Verify deactivated host is not selectable
- Preconditions: Host is deactivated.
- Steps:
  1. Confirm Host dropdown is opened.
- Expected Result: Deactivated employee is not available.
- Actual Result: No access to deactivate hosts.
- Status: [blocked]

### TC-22 Verify check-out of active visitor
- Preconditions: Visitor is active.
- Steps:
  1. Confirm Check Out is clicked for visitor.
- Expected Result: Visitor is removed from Active Visitors.
- Actual Result: Visitor removed successfully.
- Status: [pass]

### TC-23 Verify checked-out visitor is no longer active
- Preconditions: Visitor is checked out.
- Steps:
  1. Confirm page is refreshed.
- Expected Result: Visitor does not appear in Active Visitors.
- Actual Result: Visitor not appearing after checkout.
- Status: [pass]

### TC-24 Verify correct visitor is checked out
- Preconditions: Multiple visitors are active.
- Steps:
  1. Confirm Check Out is clicked for one visitor.
- Expected Result: Only selected visitor is checked out.
- Actual Result: Correct visitor checked out.
- Status: [pass]

### TC-25 Verify repeat registration after checkout
- Preconditions: Visitor is checked out.
- Steps:
  1. Confirm visitor is registered again.
- Expected Result: Visitor is allowed to register again.
- Actual Result: Visitor registered again successfully.
- Status: [pass]

### TC-26 Verify deactivated visitor not shown in active list
- Preconditions: Visitor record is deactivated.
- Steps:
  1. Confirm Active Visitors list is refreshed.
- Expected Result: Deactivated visitor doesnotappear.
- Actual Result:  deactivated visitors still appears.
- Status: [fail]

### TC-27 Verify deactivated visitor cannot be registered for repeat visit
- Preconditions: Visitor record is deactivated.
- Steps:
  1. Confirm attempt to register deactivated visitor.
- Expected Result: Visitor is not available for repeat visit.
- Actual Result: Deactivated visitors can be registered again.
- Status: [fail]

### TC-28 Verify duplicate registration
- Preconditions: Visitor is registered
- Steps:
  1. register visitor with identical information as registered visitor
- Expected Result: dublication resistration not allowed
- Actual Result: Visitor registered successfully.
- Status: [fail]



---

## Boundary & Pagination Cases

### TC-29 Verify active list pagination
- Preconditions: More than 20 visitors registered.
- Steps:
  1. Confirm 21 visitors are registered.
  2. Confirm Active Visitors list is displayed.
- Expected Result: Only 20 records appear per page.
- Actual Result: Pagination worked correctly.
- Status: [pass]

### TC-30 Verify navigation to next page
- Preconditions: More than 20 visitors registered.
- Steps:
  1. Confirm Next button is clicked.
- Expected Result: Remaining visitors are displayed on next page.
- Actual Result: Next button worked correctly.
- Status: [pass]

### TC-31 Verify navigation to previous page
- Preconditions: More than 20 visitors registered, currently on page 2.
- Steps:
  1. Confirm Previous button is clicked.
- Expected Result: Page 1 is displayed.
- Actual Result: Previous button worked correctly.
- Status: [pass]

### TC-32 Verify Next button disabled on last page
- Preconditions: Navigate to last page of visitors.
- Steps:
    1. click next button
- Expected Result: next button deactivated.
- Actual Result: next button deactivated.
- Status: [fail]


## TC-33 Verify Next button remains enabled after multiple checkouts
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




---

### API Test Cases

### TC 34: Verify Visitors API returns visitor records
Category: Happy Path
- Precondition: Application API is running.
Steps:
  1. Open Postman.
  2. Confirm the request method is GET.
  3. Confirm the endpoint is `/api/visitors'.
  4. Check the response.
- Expected Result: API returns a successful response and visitor records are displayed.
Status: [pass ]


#### TC 35: Verify Visitors API response status code
Category: Happy Path
- Precondition: Application API is running.
Steps
  1. Open Postman.
  2. Confirm the request method is GET.
  3. Confirm the endpoint is `/api/visitors'.
  4. Send the request.
  5. Check the response status code.
- Expected Result:API returns HTTP 200 status code.
 - Status: [ pass]


 ### TC 36: Verify visitor can be created using valid information through API
- Category: Happy Path
- Precondition:  Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm valid visitor information is included in the request body.
  5 Send the request.
  6 Check the response.
- Expected Result:Visitor is created successfully and the API returns the created visitor information.
- Status: [ pass]


#### TC 37: Verify visitor creation with missing Full Name
- Category: Negative
- Precondition: Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm Full Name is empty or omitted.
  5 Confirm valid values are provided for the other required fields.
  6 Send the request.
  7 Check the response.
- Expected Result
- API rejects the request and returns an appropriate validation error.
- Status: [ fail]


### TC 38: Verify visitor creation with missing Company
- Category: Negative
- Precondition: Application API is running.
- Steps:
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm Company is empty or omitted.
  5 Confirm valid values are provided for the other required fields.
  6 Send the request.
  7 Check the response.
- Expected Result: API rejects the request and returns an appropriate validation error.
- Status: [ fail]


### TC 39: Verify visitor creation with missing Host
- Category:Negative
- Precondition: Application API is running.
- Steps:
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm Host is empty or omitted.
  5 Confirm valid values are provided for the other required fields.
  6 Send the request.
  7 Check the response.
- Expected Result: API rejects the request and returns an appropriate validation error.
- Status: [ fail]


### TC 40: Verify visitor creation with missing Purpose
- Category: Negative
- Precondition:Application API is running.
- Steps:
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm Purpose is empty or omitted.
  5 Confirm valid values are provided for the other required fields.
  6 Send the request.
  7 Check the response.
- Expected Result: API rejects the request and returns an appropriate validation error.
- Status: [ fail]


### TC 41: Verify single character Full Name through API
- Category: Boundary
- Precondition: Application API is running.
- Steps:
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm `A' is entered as the Full Name.
  5 Confirm valid values are provided for the other fields.
  6 Send the request.
  7 Check the response.
- Expected Result: API validates the Full Name according to the defined business rule.
- Status:[ fail]


###  TC 42: Verify whitespace-only Full Name through API
- Category: Negative
- Precondition: Application API is running.
- Steps:
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm only spaces are entered in the Full Name field.
  5 Confirm valid values are provided for the other fields.
  6 Send the request.
  7 Check the response.
- Expected Result: API rejects the whitespace-only Full Name and returns an appropriate validation error.
- Status: [ fail]


### TC 43: Verify numeric-only Full Name through API
- Category: Negative
- Precondition: Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm `123456' is entered as the Full Name.
  5 Confirm valid values are provided for the other fields.
  6 Send the request.
  7 Check the response.
- Expected Result: API handles the numeric-only Full Name according to the defined business rule.
- Status: [ pass]


### TC 44: Verify extremely long Full Name through API
- Category: Boundary
- Precondition: Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm an extremely long value is entered in the Full Name field.
  5 Confirm valid values are provided for the other fields.
  6 Send the request.
  7 Check the response.
- Expected Result: API handles the long input safely without a server error or malformed response.
- Status: [ pass]


### TC 45: Verify duplicate visitor registration through API
- Category: Negative
- Precondition: A visitor with the same information already exists.
- Steps
  1 Open Postman.
  2 Confirm the request method is POST.
  3 Confirm the endpoint is `/api/visitors'.
  4 Confirm the same visitor information is included in the request body.
  5 Send the request.
  6 Check the response.
- Expected Result: API handles duplicate visitor registration according to the defined business rule.
- Status: [fail ]

### TC 46: Verify visitor search API
- Category: Happy Path
- Precondition:Application API is running and visitor records are available.
- Steps
  1 Open Postman.
  2 Confirm the request method is GET.
  3 Confirm the endpoint is `/api/visitors/search'.
  4 Confirm a valid search query is provided.
  5 Send the request.
  6 Check the response.
- Expected Result: API returns visitor records matching the search criteria.
- Status: [pass ]


### TC 47: Verify search for non-existing visitor
- Category: Negative
- Precondition: Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is GET.
  3 Confirm the endpoint is `/api/visitors/search'.
  4 Confirm a search value that does not exist is provided.
  5 Send the request.
  6 Check the response.
- Expected Result:API returns an empty result or appropriate response indicating that no matching visitor was found.
- Status:[pass ]


### TC 48: Verify visitor check out through API
- Category: Happy Path
- Precondition: An active visitor exists.
- Steps:
  1 Open Postman.
  2 Confirm an active visitor ID is available.
  3 Confirm the request method is PATCH.
  4 Confirm the endpoint is `/api/visitors/:id/check_out'.
  5 Replace `:id' with the active visitor ID.
  6 Send the request.
  7 Check the response.
- Expected Result: Visitor is successfully checked out and the API returns an appropriate response.
- Status:[ pass]


### TC 49: Verify check out of non-existing visitor
- Category: Negative
- Precondition: Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is PATCH.
  3 Confirm the endpoint is `/api/visitors/:id/check_out'.
  4 Confirm a non-existing visitor ID is used.
  5 Send the request.
  6 Check the response status code.
- Expected Result: API returns an appropriate 4xx error response.
- Status: [pass ]


### TC 50: Verify already checked out visitor
- Category: Negative
- Precondition: A visitor has already been checked out.
- Steps
  1 Open Postman.
  2 Confirm the visitor has already been checked out.
  3 Confirm the request method is PATCH.
  4 Confirm the endpoint is `/api/visitors/:id/check_out'.
  5 Confirm the ID of the already checked-out visitor is used.
  6 Send the request.
  7 Check the response.
- Expected Result: API handles the request appropriately and does not create an invalid visitor state.
- Status: [ pass]


### TC 51: Verify visitor deactivation through API
- Category: Happy Path
- Precondition: An active visitor exists.
- Steps
  1 Open Postman.
  2 Confirm an active visitor ID is available.
  3 Confirm the request method is PATCH.
  4 Confirm the endpoint is `/api/visitors/:id/deactivate'.
  5 Replace `:id' with the visitor ID.
  6 Send the request.
  7 Check the response.
- Expected Result: Visitor is successfully deactivated and the API returns an appropriate response.
- Status: [fail ]


### TC 52: Verify deactivation of non-existing visitor
- Category: Negative
- Precondition: Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is PATCH.
  3 Confirm the endpoint is `/api/visitors/:id/deactivate'.
  4 Confirm a non-existing visitor ID is used.
  5 Send the request.
  6 Check the response status code.
- Expected Result: API returns an appropriate 4xx error response.
- Status: [ fail]


### TC 53: Verify already deactivated visitor
- Category: Negative
- Precondition: A visitor has already been deactivated.
- Steps
  1 Open Postman.
  2 Confirm the visitor has already been deactivated.
  3 Confirm the request method is PATCH.
  4 Confirm the endpoint is `/api/visitors/:id/deactivate'.
  5 Confirm the ID of the already deactivated visitor is used.
  6 Send the request.
  7 Check the response.
- Expected Result: API handles the request appropriately and does not create an invalid visitor state.
- Status:[ fail]


### TC 54: Verify Hosts API
- Category: Happy Path
- Precondition: Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is GET.
  3 Confirm the endpoint is `/api/hosts'.
  4 Send the request.
  5 Check the response.
- Expected Result: API returns a successful response containing the available hosts.
- Status:[ pass]


### TC 55: Verify Hosts API response status code
- Category:Happy Path
- Precondition: Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is GET.
  3 Confirm the endpoint is `/api/hosts'.
  4 Send the request.
  5 Check the response status code.
- Expected Result: API returns HTTP 200 status code.
- Status: [ pass]


## #TC 56: Verify invalid visitor endpoint
- Category: Negative
- Precondition: Application API is running.
 - Steps:
  1 Open Postman.
  2 Confirm an invalid visitor endpoint is entered.
  3 Confirm the request is sent.
  4 Check the response status code.
- Expected Result: API returns an appropriate 4xx error response.
- status: [ pass]


### TC 57: Verify invalid visitor ID during check out
- Category: Negative
- Precondition: Application API is running.
- Steps:
  1 Open Postman.
  2 Confirm the request method is PATCH.
  3 Confirm the endpoint is `/api/visitors/:id/check_out'.
  4 Confirm an invalid visitor ID is used.
  5 Send the request.
  6 Check the response.
- Expected Result: API handles the invalid ID appropriately and does not return an unexpected server error.
- Status: [pass ]


### TC 58: Verify invalid visitor ID during deactivation
- Category: Negative
- Precondition: Application API is running.
- Steps
  1 Open Postman.
  2 Confirm the request method is PATCH.
  3 Confirm the endpoint is `/api/visitors/:id/deactivate'.
  4 Confirm an invalid visitor ID is used.
  5 Send the request.
  6 Check the response.
- Expected Result: API handles the invalid ID appropriately and does not return an unexpected server error.
- Status: [ pass]

