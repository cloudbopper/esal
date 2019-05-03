Story 1: Count events in a stream
=================================


Count the total number of events or count the total number of
occurrences of a selected event (e.g. warfarin prescriptions) in a
stream of events.

An event should be able to represent something happening at a point in
time or over a period of time.  It should be able to represent a
measurement or sample taken at a particular time.

The intended domain is medical events in electronic health records.

* Raw count of events (no grouping, what is selected is what is counted)
* Selection criterion is event field matching a single value
* Selection criterion can be omitted
* Report is a single number
* User will interact with API at Python prompt and set up the event
  stream themselves


Design
------

* An event is a (sequence_id, start_time, duration, event, value) tuple

* A stream is an iterable of events

* Field names will be mapped to event tuple indices for access

* Selection applies a predicate to each tuple and returns those for
  which the predicate is true

* Predicate-aware selection (which can be optimized based on the
  predicate) can be designed later.  (What I have written already is
  predicate-aware selection.)

* func select(events: event stream, predicate: func(tuple): bool): event
  stream

* func count(events: event stream): int


-----
Copyright (c) 2015 Aubrey Barnard.  This is free software.  See LICENSE
for details.
