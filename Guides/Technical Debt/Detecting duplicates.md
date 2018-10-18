# Detecting duplicate code

## Types of duplicates and what to do about them
At a project level:
How many active branches do you have? 
- If you receive a change request or bug report, how many branches would potentially need merge and re-test?
How many maintenance branches do you have?
- If a released software needs modification (e.g., migration to a new 3rd party library version), how many branches would need the modification?

At the code level (within the active branch):
1. Same expressions close together (e.g.in same class): Extract method
2. Same expressions far away (different classes or modules): Some more extraction required
3. Similar but not same code: first separate the same parts from not-same parts, usually comes from extraction of name-able code-sequences
4. Same outcome with different classes/algorithms/libraries: Choose the one that's simpler, usually the most difficult

In addition: Branching can create a copy of the whole archive

At what events does duplication happen? 
- A developer needs to do something similar to what has been done before: Copy-paste the code
- We want to try a newer library to do something, but not sure if it will work. By the time we make it work, it's time for delivery
- Common code was put in a function. However it turned out that different callers needed different things. So branching happened
-->These are 'duplication-events'

How do we detect duplicates?
Method1: From the smells. Do you find yourself needing to fix a bug on multiple branches? Fix and test multiple scenarios? Fix in multiple places in the code?
Method2: Recognizing a duplication-event and logging a defect
Method3: Comparing code
