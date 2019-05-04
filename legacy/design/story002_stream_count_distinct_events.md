Story 2: Count distinct events in a stream
==========================================


Count the number of event sequences (e.g. patients) in a stream of
events.  Count the number of event types.

* Count of distinct/unique values of a given event field
* What is selected is what is counted
* No criterion
* Report is a single number
* User will interact with the API at the Python prompt


Design
------

* Distinctness will apply to complete items/tuples, just like in a DB

* Therefore, events must be transformed (e.g. projected) to keys before
  distinct counting

* Since this is a low-level API, use indices to indicate fields

* Algorithm: add items to a set, return size of set.  Thus items must be
  hashable.

* func project(events: event stream, fields: iterable of indices): item stream

* func distinct(items: iterable of hashable): set of items


-----
Copyright (c) 2015 Aubrey Barnard.  This is free software.  See LICENSE
for details.
