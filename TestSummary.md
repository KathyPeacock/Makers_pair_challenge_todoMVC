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


Tests Performed:

TEST 1 **Can't add an item with an empty value**
TEST 2 **Can add a value with a single character** `FAILED`
TEST 3 **Can delete a single item** 
TEST 4 **Can add characters and symbols** - some individual inputs `FAILED`
TEST 5 **Can add emoji characters**
TEST 6 **Can modify existing todo item**
TEST 7 **Pressing Escape during item modification cancels modification**
TEST 8 **Can add another todo item to list**
TEST 9 **Can reorder items** `FAILED`
TEST 10 **Can mark an item complete**
TEST 11.1 **Can filter incompleted items** 
TEST 11.2 **Can filter completed items** 
TEST 11.3 **Can filter by all items**
TEST 12 **Can mark an item incomplete**
TEST 13 **Can mark all todo items as complete**
TEST 14 **Can mark all todo items as incomplete**
TEST 15 **Can clear complete todo items when >0 completed todo items are listed**
CONFIRM Status bar always displays a count of remaining todo items left to do? ('Always' in scope of this basic function test)

Full details of tests, supplementary tests undertaken during test process, and results can be found in TestNotes.md 


## Overall Impression of Quality

Product cannot be released in current state. 

The product performs all the basic specified functions correctly, with results as expected - EXCEPT the item reordering function which cannot be performed (see bug report). 

Bug reports have been created on GitHub Issues.

Highest severity bug is deemed to be the above reordering function as this is a key basic function listed in the user specification and is currently not usable.

Medium severity bug has been reported concerning punction inputs. Certain special symbols/punction marks - many of which could be predicted as a common imput for our user needs - when inputted display as incorrect collections of symbols on created todo item (see bug report).

There were a few small unexpected results, ie 'failed' tests that are not deemed urgent as they do not contradict anything in the user spec - eg it was discovered that an input of one character does not work - input has to be more than 2 characters. Also, error message expected for invalid inputs is not present (but recommended before release.)

