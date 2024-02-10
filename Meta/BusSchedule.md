# Bus Schedule

Given an array of strings schedule that represents the schedule of bus departure times and a string time that represents the current time, find out how many minutes ago the last bus left. If the first bus for the day has yet to leave, return -1.

Time is represented as a string in the form of HH:MM (in the 24-hour format). Bus departure times are sorted in chronological order.

Please assume that if a bus is scheduled to leave at the current time, it hasn't left yet.

Note: You are not expected to provide the most optimal solution, but a solution with time complexity not worse than o(schedule.length x MINUTES_IN_DAY) will fit within the execution time limit.
### Example
- For schedule = ["12:30", "14:00", "19:55"]
and time = "14:30", the output should be
solution (schedule, time) = 30.

Explanation:
The current time is "14:30" The last bus left at "14:00", so the answer is 30 minutes ago.

- For schedule = ["00:00", "14:00", "19:55"] and time = "00:00", the output should be
solution (schedule, time) = -1

Explanation:
No buses left before "00:00" (the bus scheduled
to leave at "00:00" hasn't left yet), so the answer
is -1.
- For schedule =
["12:30","14:00", "19:55"]
and time="14:00", the output should be
solution (schedule, time) = 90

Explanation:
The current time is "14:00". The last bus left at "12:30" (the bus scheduled to leave at "14:00" hasn't left yet), so the answer is 90 minutes agc.
