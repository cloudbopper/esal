Story 3: Count selected sequences in a stream
=============================================


Count the number of patients (event sequences) who have had a warfarin
prescription (a selected value of an event field) in a stream of events.

* What is counted is different than what is selected
* Count of distinct items
* Report is a single number
* User will construct query from API pieces


Design
------

* No need to assemble into sequences.  Just use sequence ID from
  selected events.

* Algorithm: select events with predicate -> project events to sequence
  ID key -> count distinct keys

* No new functions needed


-----
Copyright (c) 2015 Aubrey Barnard.  This is free software.  See LICENSE
for details.
