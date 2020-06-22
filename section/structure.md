---
---

# Structure #


## Worlds ##
Worlds allow you to separate drastically-different parts of your life (like _Home_ and _Work_),
much like most apps require separate accounts for.


## Groups ##
A Group is a set of Tasklists andor subgroups.

A Group can belong to exactly one World, but can be displayed, changed, and referenced in others
for convenience.


## Tasklists ##
A Tasklist is a set of tasks. Obviously.

A Tasklist can belong to exactly one Group, but can be displayed, changed, and referenced in others
for convenience.

A Tasklist can be recurring or one-shot. When recurring tasklists recur, their completion state is
reset.


## Tasks ##
A Task is a myopic item that must be completed. Tasks can contain subtasks (which are also Tasks).

A Task is considered complete when all its subtasks are also complete.

Tasks can belong to exactly one Tasklist, but can be displayed, changed, and referenced in others
for convenience.

A Task can be recurring or one-shot.
- When recurring tasks recur, their completion state is reset.
- The recurring/one-shot property is inherited from the task's list by default, but can be changed.
- One-shot tasks within recurring tasks and tasklists are _not_ reset when the tasklist recurs.
- Recurring tasks within recurring tasks and tasklists share the same recur interval as their
  parent, and this cannot be changed.
