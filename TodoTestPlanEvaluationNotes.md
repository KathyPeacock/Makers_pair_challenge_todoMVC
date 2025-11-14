# TodoMVC Test Plan - Quality Evaluation Notes

**Date:** November 13, 2025  
**Exercise:** Partner Challenge - Test Plan Evaluation  
**Context:** Evaluating whether the test plan is suitable for launching TodoMVC in the next few days

---

### Summary of Key Issues:

**Critical Problems:**
1. **Unrealistic timeline** - 216 hours of work required in "a few days"
2. **No test environment** - testing directly in production
3. **Incomplete documentation** - character limit undefined, entry criteria incomplete
4. **Resource constraints** - insufficient experienced testers
5. **Contradictory exit criteria** - quality vs. deadline **Also no working entry criteria**

---


## 1. What do you like about the plan?

### Strengths Identified:

**Clear Structure & Documentation**
- Well-organized with version history (shows revision tracking) **(is it missing versions?)**
- Clear sections that follow logical test planning structure
- Includes specific technical details about local storage implementation

**Comprehensive Feature Coverage**
- Detailed list of features to test (add, modify, delete, filter, reorder items)
- Considers edge cases like empty values, single characters
- Plans to test character encoding and emojis
- Cross-variant testing to ensure data isolation between frameworks
- Out of Scope features include some clear examples.

**Risk Management**
- Identifies 6 specific risks with mitigation strategies, and shows awareness of real-world constraints (internet access, PO availability, developer changes) - although much of this is unrealistic (see )

**Browser Coverage**
- Plans to test across 4 major browsers (Chrome, Safari, Firefox, IE)

**Team Allocation**
- Clear identification of team members and their experience levels
- Realistic time estimation (1 hour per variant per browser)

---


## 2. Does it feel like anything important is missing from the plan?

**Missing detail of tracking changes/revisions**
- ...aside from just dates etc

### Critical Omissions:

**Launch timeframe ambiguity**
- Shipping in 'few days' time' - critical missing info that has implications on time estimation, testability, scheduling and prioritisation etc.

**Scope features not specified**
- We are told that the in scope features to test are the 'most popular ones' with no indication of what those are.
- also **contradiction** of specifying that keyboard navigation is not yet implemented, yet including key strokes in tests.

**Lack of consistency in terminology and syntax**
- product features/functions can be inconsistently named (eg 'active/completed' items/ completed or incomplete items...)
- eg 'clear completed' technically not a link.

**Missing Test Cases & Scenarios**
- No negative testing specified (beyond "can't add empty item")
- Missing boundary testing for the character limit (states "??" - undefined limit!)
- No error handling scenarios defined
- No testing for data persistence across browser sessions/refreshes
- Individual delete functionality mentioned in requirements but not in detailed test cases
- No acceptance criteria defined for each feature
- 'No items left' and 'remaining' text inconsistencies/ambiguities
- Not testing all items being checked as incomplete
- Not testing rearranging items

**Incomplete Entry/Exit Criteria**
- Entry criteria includes "(todo: add more criteria)" - literally incomplete
- No definition of what constitutes a "passed" test
- Exit criteria allows shipping with unfixed bugs ("whichever comes first")

**Missing Test Data Strategy**
- No test data preparation plan
- No examples of test scenarios or test case documentation
- No clear pass/fail criteria for individual tests
- Missing case sensitive test

**Configuration Management Issues**
- No clear definition of what "Build 1.0" means
- No process for test environment setup (it's "being rebuilt")
- No rollback plan if critical issues found

**Defect Management Gaps**
- No severity classification (only priority)
- No clear criteria for what constitutes each priority level
- Weekly review cadence seems too slow for imminent launch
- No retest/regression strategy mentioned

**Mobile & Accessibility**
- "Should we test on mobile devices?" is listed as out of scope but left as a question
- No accessibility testing mentioned
- Keyboard navigation explicitly excluded as "not yet implemented"

**Performance & Security**
- Performance testing delayed until after launch
- No security testing mentioned
- No load testing with multiple items

---


## 3. Does any of the testing feel unnecessary?

### Potentially Excessive Testing:

**Character & Emoji Testing**
- "Check that every single accented character and symbol is supported"
- "Check that every single emoji character is supported"
- **Why excessive:** This could mean testing thousands of characters. More practical would be representative sampling from different Unicode ranges or character sets.

**Granular Item Count Testing**
- Testing "0 items left", "1 item left", "2 items left", "3 items left" separately
- **Why excessive:** Testing 0, 1, 2, and plural (e.g., 5) would be sufficient 

**Testing All 54 Variants**
- Planning to test all 54 framework variants with identical functionality
- **Why excessive:** Given time constraints and identical spec, testing a representative sample (e.g., 5-10 most popular) would be more realistic, with smaller tests on others.

**Internet Explorer Testing**
- Testing latest version of IE is unnecessary as essentially obsolete.
- **Why unnecessary:** IE is no longer supported by Microsoft; modern Edge would be more relevant

**Local Storage Implementation Details**
- Deep verification of UUID format and JSON structure
- **Why excessive:** This is backend detail rather than user-facing functionality.

**Mobile Device Testing Question**
- Should we test on mobile devices? Why only just being raised? In this day and age you should, but why suddenly now? But in this context is it out of scope… ? 
- Also testing on production environment - the devs will likely be working on desktop...
- Unrealistic to add whole new mobile tests with different browsers etc on top.

---


## 4. Does any of the testing seem unrealistic? (Site launches in a few days!)

### Major Unrealistic Expectations:

**'Free of Bugs' shipping criteria contradiction**
- An exit criteria of 'free of bugs', but will be shipping on an immovable date 'regardless', is a critical inconsistency of expectation.

**Timeline vs. Scope Mismatch**
- **216 hours of testing** (54 variants × 4 browsers) divided by 3 testers = **72 hours per person**
- That's nearly **2 weeks of full-time testing** for a launch "in a few days". We can consider it 2 testers, if the person is not experienced or even onboarded.
- **Conclusion:** Mathematically impossible.

**Resource Constraints**
- Only 3 testers available (4 out of 7 on other projects)
- One tester (C.Chapel) joined last week and is still onboarding
- **Reality check:** A new hire won't be productive on complex testing immediately

**Test Environment Issues**
- Test environment is "being rebuilt" and unavailable, so plan is to test directly in PRODUCTION environment.
- **Risk:** Could break production before launch; no safe testing space; development and changes in progress while live testing.

**Too many browsers to test**
- Plan requires testing of all functionalities across all in-scope features, on multiple browsers. This is extremely time consuming and shouldn't be a priority. (Smaller tests can be done on main priority functions/features across browsers.)

**Immovable Ship Date**
- "We cannot move the ship date"
- Yet exit criteria allows shipping with unfixed bugs
- **Contradiction:** This isn't really a quality gate, it's a calendar date

**Overtime Assumption**
- Risk mitigation: "Test team will work overtime until tests are finished"
- **Unrealistic:** This assumes unlimited capacity and ignores human factors/burnout

**Weekly Defect Reviews**
- Defects reviewed weekly by panel
- **Timeline issue:** With launch in "a few days," bugs need daily or real-time triage. Also testers required to be reviewers and fixers also, on top of already identified constraints to their testing.

**Hiring Temporary Developers**
- Listed as mitigation if too many bugs found
- **Unrealistic:** Can't hire, onboard, and have developers fix bugs in a few days

**100% Coverage Requirement**
- Coverage criteria demands testing ALL functional requirements across ALL in-scope frameworks
- **Conflict:** Objective acknowledges "ship date cannot move" but requires complete coverage. 

---


## 5. If you were the tester executing this plan, where might you struggle?

### Practical Execution Challenges:

**Ambiguity, Error & Lack of Detail**

**Entry Criteria**
- Lacking and fundamentally incomplete
- **contradiction** criteria is to wait until 1.0 is released...

- **Character limit is "??"** - Cannot test without knowing the actual limit
- No clear test cases or step-by-step procedures provided
- "Latest version" of browsers - need specific version numbers for reproducibility.

**Priority in JSON information is an integer**
- ...but written in plan as string**

**Instruction ambiguity**
- Unclear where exactly to click for checking and unchecking boxes.
- Toggling down button function (also brings in fact that key navigation unfinished)

**No Test Documentation Templates**
- No test data provided
- How should test results be recorded?
- What format for test cases?
- Where to document actual vs expected results?
- Further clear documentation process outline required (bug reporting as well as general documentation)

**Priority vs. Risk Confusion**
- Priority 1 = "immediate attention" but defects reviewed weekly
- Priority 2 = "fixed today" but who decides this?
- No guidance on how to assess priority

**Test Environment Problems**
- Testing in production is dangerous and unprofessional
- No way to reset data between test runs
- Could interfere with other testers' work
- Risk of breaking the site before launch

**No Clear Definition of "Done"**
- When is a test considered passed?
- How many times should tests be repeated?
- What constitutes sufficient evidence?

**Isolation & Data Management**
- Local storage means each tester's work is isolated to their machine/browser
- Hard to share state or reproduce issues
- No test data cleanup strategy

**New Team Member Onboarding**
- C.Chapel is still onboarding - how will they learn the product?
- No mention of training or knowledge transfer
- Unrealistic to expect full productivity

**Scope Uncertainty**
- "Most popular frameworks" not defined - which specific ones?
- Unclear if testing the same 54 or a subset
- Statement "we can test less popular frameworks after release" conflicts with coverage goals

**Communication Gaps**
- Product Owner on holiday - who makes decisions?
- Developers on another project soon - who fixes bugs?
- No daily standup or sync mechanism mentioned
- Bad internet warned, and home working in place

**Contradictory Exit/Success Criteria**
- Pass/fail: "no more bugs remaining"
- Exit criteria: "no more bugs OR ship date, whichever comes first"
- Which one actually matters?

**Manual Testing Inefficiency**
- All testing appears manual (no mention of automation)
- Highly repetitive work (216 combinations) in short time = prone to human error

---


## Overall Assessment

**Bottom Line:**
This test plan is **not suitable** for a launch in a few days. It demonstrates understanding of what to test but lacks practical execution strategy, has unrealistic time estimates, ineffective risk mitigation, and contains critical gaps that would prevent successful execution. The team would need to significantly reduce scope, prioritize ruthlessly, and implement risk-based testing to have any chance of meaningful quality validation before launch.

---

