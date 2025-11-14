# TodoMVC Test Plan

## Author
Benjamin Loveday + Kathy Peacock
## Date 
13 Nov 2025
## Launch 
17 Nov 2025 (3 days)

---

# SUMMARY OF PRODUCT
TodoMVC is a website which collates examples of the same "To-Do List" application implemented in all of the different JavaScript frameworks. Developers can utilise these examples when evaluating what framework they would like to use for their own application development.

***Note on Storage*** 
The simple to-do list application doesn't have any persistent storage; it stores its data in the user's local storage (see "Features To Be Tested" for more information about this). Consequently, the application is not designed to be a real-world to-do list manager, as there's no way to share the data between sessions, browsers or machines.

---

# ASSUMPTIONS
- working days include weekends
- React, Angular, Mithril, Lit, Dojo - these are the 5 most popular frameworks.
- new joiner to testing is still onboarding and won't be able to independently test. (Assume team of 2)
- Assume test environment won't be fixed
- Devs will not be adding new functionality/making changes unrelated to bug/issue fixing
- Assuming PO on holiday and someone has been assigned Acting PO.
- Release day can be pushed if Priority 1 and 2 bugs remain
- Test data has been generated as per plan
- Testing in English only

# OBJECTIVES
- outline testing which will be performed to ensure key functionality (outlined in Coverage Criteria) of most popular framework (outlined in Scope)
- validate critical user journeys
- identify, prioritise and rectify highest risk bugs

# SCOPE
- 5 most popular frameworks only:
REACT, ANGULAR, MITHRIL, LIT, DOJO
- Testing using: Chrome browser (latest stable = v142.0+). Safari browser (latest stable = v17+).
- ***NB:*** We will only be testing the examples which are hosted on the website; GitHub links, download links and blogs are out-of-scope.

## Coverage Criteria
1. New todo items can be added
2. Todo items can always be modified
3. Todo items can always be individually deleted
4. A todo item can be marked completed or incomplete
5. All todo items can be marked as completed, whether they have been completed or not
6. If all todo items are marked as completed, they can all be marked as incomplete in one go
7. The list can be filtered on todo items' completion states
8. Complete todo items can be cleared from the list, when >0 completed todo items are listed
9. Status bar always displays a count of remaining todo items left to do
10. Todo items can be reordered

## Success Metrics
**Coverage Goal** = complete all listed manual tests, prioritise and log all bugs and defects, ensure all high priority issues (Priority 1 + 2) are rectified and re-validated. Any existing Priority 3 issues are logged, communicated to Acting PO. 

# OUT OF SCOPE
- Other browsers
- Other frameworks of the product
- sidebar links (Official Resources, Community, etc) for each template
- Keyboard navigation - not yet implemented
- Mobile devices
- Specific accessibility testing further than standard user functionality
- Load testing + security testing
- Testing the persistence of local storage between frameworks
- Non-English languages

---


# RESOURCES

## TEST ENVIRONMENTS
Due to unavoidable limitations, we will be running tests against the production website (https://todomvc.com) (not officially released) (product testing risks are acknowledged by Acting PO.)
- Chrome browser v119+
- Safari browser (latest stable = v17+).

## TEST TEAM
2 experienced testers.

## TEST DATA
20 'todo' items that ensure coverage of input characters, special characters, emoji, cases, integers, white space and length limits.

## Features To Be Tested

`TEST 1` **Can't add an item with an empty value**
          
`TEST 2` **Can add a value with a single character**
       
`TEST 3` **Delete individual todo item**

`TEST 4` **Can add characters and symbols**
       
`TEST 5` **Can add emoji characters**

`TEST 6` **Can modify existing todo item**

`TEST 7` **Pressing Escape during item modification cancels modification**

`TEST 8` **Can add another todo item to list**

`TEST 9` **Can reorder items**

`TEST 10` **Can mark an item complete**

`TEST 11` **Can filter items by status**

`TEST 12` **Can mark an item incomplete**

`TEST 13` **Can mark all todo items as complete**

`TEST 14` **Can mark all todo items as incomplete**

`TEST 15` **Can clear complete todo items when >0 completed todo items are listed**


`SUPPLEMENTARY TEST` Status bar always displays a count of remaining todo items left to do



## EDGE CASE TESTS
See test case doc.

## Test Estimation
For a single variant, in a single browser, we estimate that it will take around 50 mins to complete a single cycle. 10 minutes test admin/bug reporting = 1 hour. 
5 variants and 2 browers = 1 x 5 x 2 = 10 hours.

This leaves time for standup/test triage, prioritisation, chasing and fix-validation.



# COMMUNICATION PLAN
- Daily Standup (can be reevaluated with time constraints)
- Daily Defect Triage
- Bugs logged on GitHub
- Urgent comms on Slack


## Entry Criteria
To commence when all resources are available.
Browsers are installed, testers are briefed on report process and format.
Test lead is briefed on test plan.

## Exit Criteria
Best case: All tests pass for all 5 features on both browsers.
All significant/high priority bugs are fixed. (Priority 1 and 2).
Priority 3 bugs fixed as best case. Any existing Priority 3 issues are logged, communicated to Acting PO. Acting PO signs off for release.  

# RISKS 
| **Risk** | **Severity** | **Likelihood** | **Mitigation** |
|:---------|:-------------|:---------------|:---------------|
| ***Product Owner on holiday*** | High | High | Clear Documentation. Established new chain of command in their place. |
| ***Test environment unavailable*** | High | High | Devs will not make changes and additions during testing period. Devs will not deploy any new versions. |



# BUG REPORT STANDARDS

Title
Priority (1-3, with 1 being most severe)

Date and Time
Name of tester
Environment
Description
Steps to Replicate
Screenshots/other documentation if necessary