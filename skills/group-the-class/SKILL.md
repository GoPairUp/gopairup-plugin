---
name: group-the-class
description: Make, shuffle or adjust a class's groups in GoPairUp. Use when a teacher asks to group or pair up students, make groups or centers for today, shuffle groups, says who is absent or out, or wants two students kept apart or moved.
---

# Group the class

Use the GoPairUp connector's tools. Work from what the teacher said; ask only when the class
or the number of groups is unclear.

1. **Find the class.** Call `list_classes`. If the teacher named a class, match it by name;
   if they didn't and there are several, use the one marked `selected`, and say which you used.
2. **Read it.** Call `get_class` for the roster, today's absences, the current groups and the
   keep-apart pairs. Use the student and group ids it gives; never guess an id.
3. **Today's date.** The tools that deal students take `today` as `YYYY-MM-DD`. Use the
   teacher's local date.
4. **Absences first.** For each student the teacher says is out, call `mark_absent` with
   `today`. Absent students sit out today's groups and come back tomorrow.
5. **Keep-apart pairs.** For "keep X and Y apart", call `set_keep_apart`. It moves no one, so
   if they share a group now, move one of them or shuffle.
6. **Make or shuffle.**
   - New groups: call `make_groups` with the number of groups. If the teacher gave a group
     size instead, divide the students here today by it and round to the nearest whole number.
     This replaces every group, locked ones too, so confirm first if the class already has
     groups the teacher may have arranged by hand.
   - Same groups, new mixes: call `shuffle_groups`. It keeps locked groups and group names.
   - One change: call `move_student`. If it's refused because of a keep-apart pair, tell the
     teacher and only pass `allow_together_with` if they say to put them together anyway.
7. **Answer briefly.** List each group by name with its students' first names, and mention
   who is out. Don't paste the tool's raw output or ids.

If a tool says the classes kept changing or asks you to call `get_class` again, do that and
retry once. If GoPairUp reports a problem on its side, tell the teacher and check with
`get_class` before trying a change again.
