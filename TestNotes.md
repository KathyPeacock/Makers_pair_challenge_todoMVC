
# TodoMVC Test 1 (Basic Functionality)

## Timebox: 
45 mins test. 10 mins bug reporting.

## Testers: 
Benjamin Loveday (Driving)
Kathy Peacock (Documentation)

## Date 
14 Nov 2025

## Test time
Begin: 12.18
End: 13.03

## Environment
Chrome latest stable = v142.0+ 
Framework: React
https://todomvc.com/examples/react/dist/

# Test Checklist

[x] TEST 1 **Can't add an item with an empty value**
    - Click into input field.
    - Press Enter
    - Expected Outcome: Nothing added. Possible error message. Status bar hidden.
    - Actual Outcome: Nothing added. No error message. Status bar hidden

    TEST ADDED - Tested with white space 1,2,3 clicks - also nothing as expected.

[x] TEST 2 **Can add a value with a single character**
    - Click into input field
    - Type `k`
    - Press Enter
    - Expected Outcome: New todo item added to list: `k`. Status bar updates to `1 item left!`.
    - Actual Outcome: Nothing added or changed. 

    TEST ADDED - `kk` adds as expected.

[x] TEST 3 **Can delete a single item** 
    - Click cross by todo item
    - Expected Outcome: Todo item removed. Status bar hidden.
    - Actual Outcome: As expected. 

[x] TEST 4 **Can add characters and symbols**
    - Before Each: Click into input field
    - Input
    - Press Enter. 
    - After Each: Log result. Delete item.

    - Expected Outcome: Correct todo item added to list and appears as incomplete. Status bar updates.

        [x] Test-with-dashes_and_underscores
        [x] Test/with\slashes
        Actual outcome: Test&#x2F;with\slashes
        screenshot1

        [x] Test with 'single' and "double" quotes
        Actual outcome: Test with &#x27;single&#x27; and &quot;double&quot; quotes
        screenshot2

        [x] Test with @#$%^&*()
        Actual outcome: Test with @#$%^&amp;*()
        screenshot3 (highlighted what appeared for &)

        [x] Test with brackets [square] {curly} (round)

        [x] Test with <angle> brackets
        Actual outcome: Test with &lt;angle&gt; brackets
        screenshot4 (highlighted <angle>)

        [x] Test with | pipe & ampersand
        Equivalence & issue again.

        [x] Test with + plus = equals

        [x] Test with ~ tilde ` backtick
        
        [x] Test with spaces and punctuation!

        [x] Café résumé naïve
        [x] Mañana niño jalapeño
        [x] München Zürich über
        [x] Bjørn Søren København
        [x] Łódź Kraków Gdańsk
        [x] São Paulo João

    ADDED TEST

    input: `,.` as expected

[x] TEST 5 **Can add emoji characters**
    - Before Each: Click into input field
    - Input
    - Press Enter. 
    - After Each: Log result. Delete item.

    - Expected Outcome: Correct todo item added to list and appears as incomplete. Status bar updates.

        [x] Task complete ✅ 
        [ ] Urgent task 🚨
        [ ] Celebration 🎉
        [ ] In progress 🔄
        [ ] Bug found 🐛
        [ ] Coffee break ☕
 
Equivalence - both text with emoji and emoji on own is fine.


[x] TEST 6 **Can modify existing todo item**
    - Click into input field
    - Enter a todo item: `make a sandwich`
    - Press Enter.
    - Double click todo item and change to `make a cake`
    - Press Enter.

    - Expected Outcome: Todo item now reads `make a cake` and appears as incomplete. Status bar remains the same (`1 item left!`).
    - Actual Outcome: As expected.

[x] TEST 7 **Pressing Escape during item modification cancels modification**
    - Double click on todo item `make a cake`
    - Press backspace until word cake is removed
    - Type `birthday cake`
    - Press Escape.

    - Expected Outcome: Todo item is not modified. Remains `make a cake` and appears as incomplete. Status bar remains the same (`1 item left!`).
    - Actual Outcome: When escape clicked, nothing happens.
    TESTED clicking outside of the input window and the expected outcome happens then. Tested clicking inside input window nothing happens.

[x] TEST 8 **Can add another todo item to list**
    - Click into input field
    - Enter a todo item: `clear up kitchen`
    - Press Enter.

    - Expected Outcome: Todo item id added. List now includes `make a cake` and `clear up kitchen`. Status for both appears as incomplete. Status bar displays correct amount of incomplete items (`2 items left!`).
    - Actual Outcome: As expected. Note: new todo item appears below existing item.

    TEST ADDED - added 3rd shorter item to test theory of ordering by order added not length.


[x] TEST 9 **Can reorder items**
    - Click and drag `make a cake` item to below `clear up kitchen` item
    
    - Expected Outcome: Todo items swap position. Status for both appears as incomplete. Status bar displays correct amount of incomplete items (`2 items left!`).
    - Actual Outcome: Clicking on text and dragging ends up highlighting text. Clicking on tab white space and dragging highlights text. Click and hold on toggle box directly over circle highlights item in red but cannot be dragged. Nothing happens (as expected) when using arrow buttons after item selected. Double click to edit shows no way to reorder.
    Seems that user cannot reorder items.



[x] TEST 10 **Can mark an item complete**
    - Click circle next to item `make a cake` to toggle on

    - Expected Outcome: `make a cake` item status displays visual indicator `complete`. Status bar displays correct amount of incomplete items (`1 item left!`).
    - Actual Outcome: As expected. Green tick appears in circle and text strike through for completed item. Text also is greyed. 
    screenshot5



[x] TEST 11.1 **Can filter incompleted items** 
    - Select `incomplete` on filter

    - Expected Outcome: Only incomplete items shown (`clear up kitchen`). Status bar remains unchanged.
    - Actual Outcome: As expected.

    NB - On website 'incomplete' is displayed as `Active`. This is contrary to language of specification.
    screenshot6



[x] TEST 11.2 **Can filter completed items** 
    - Select `complete` on filter

    - Expected Outcome: Only complete items shown (`make a cake`) Status bar remains unchanged (`1 item left!`).
    - Actual Outcome: As expected.

[x] TEST 11.3 **Can filter by all items** 
    - Select `all` on filter

    - Expected Outcome: All items shown. Status bar show correct message (`2 items left!`).
    - Actual Outcome: As expected.


[x] TEST 12 **Can mark an item incomplete**
    - Click box next to item `make a cake` to toggle off

    - Expected Outcome: `make a cake` item status displays visual indicator `incomplete`. Status bar displays correct amount of incomplete items (`2 items left!`).
    - Actual Outcome: As expected.


    TEST ADDED - Clicked Clear Completed when no completed items on list. Expected no change. Observed no change.


[x] TEST 13 **Can mark all todo items as complete**
    - Click to mark all complete

    - Expected Outcome: Both marked as complete. Status bar displays correct amount of incomplete items (`0 items left!`).

    - Actual Outcome: Outcome is as expected, however the method is not by clicking a link. This is performed by clicking the chevron above the toggle circles. Chevron darkens for all items mark complete function.

    TEST ---- Untoggling single item while mark all complete chevron function active marks item as incomplete. Status bar behaves as expected. Chevron has lightened as expected.

    TEST ---- Untoggling and retoggling both manually ie marking all items as complete manually triggers chevron darkening response.


[x] TEST 14 **Can mark all todo items as incomplete**
    - Click to mark all incomplete

    - Expected Outcome: Both marked as incomplete. Status bar displays correct amount of incomplete items (`2 items left!`).
    - Actual Outcome: As expected.

    TEST --- one item marked as complete - press chevron. Marks all as complete. Press chevron again marks all as incomplete. All have to be marked complete for 'mark all incomplete' chevron behaviour to work.

    TEST - Observe display behaviour. All marked as incomplete - click on complete as a filter. Chevron disappears. This behaviour is consistent with explored functions.
    screenshot7



[x] TEST 15 **Can clear complete todo items when >0 completed todo items are listed**
    - Click box next to item `make a cake` to toggle on
    - Click to clear complete todo items 
    
    - Expected Outcome: Completed item `make a cake` is removed from list. `clear up kitchen` item remains, with status as incomplete. Status bar displays correct amount of incomplete items (`1 item left!`).
    - Actual Outcome: As expected.


    TEST - marking all as complete and clicking clear completed clears all (as expected)

    TEST - click make cake to toggle as complete
    - filtered by incomplete/active items (can't see complete item as expected)
    - click clear completed
    - return to filter by All view
    - complete item has been removed as expected.

[x] CONFIRM Status bar always displays a count of remaining todo items left to do? ('Always' in scope of this basic function test)
NB - status bar is hidden when there are 0 items.




# FURTHER TESTS FOR NEXT SESSION:

Edge Cases to include:

**extreme input lengths**


Tab	character	test
Multiple     spaces     test
Line
break
test
Zero-width​character (has zero-width space)
Very long word: Supercalifragilisticexpialidocious
Number sequence: 1234567890


**foreign languages**


Привет (Russian - Hello)
你好 (Chinese - Hello)
こんにちは (Japanese - Hello)
안녕하세요 (Korean - Hello)
مرحبا (Arabic - Hello)
שלום (Hebrew - Hello)




**Test ordering of items is by order inputted not alphabetical, length etc.**