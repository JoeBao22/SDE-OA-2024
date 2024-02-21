# Maximum User Traffic
In order to ensure a hassle-free user experience during the festive season, Amazon maintains logs of the days when its users use the Amazon Shopping app.

The user traffic of a day is said to be the maximum number of users logged into the application during that day. If a user uses the application from day login[i] to day logout[i], it increases the traffic of each day from login[i] to logout[i] (both inclusive) by 1. That is, if login[i] = 4 and logout[i] = 6, then this user increases the traffic of days 4, 5 and 6 by 1.

Given the login and logout day data of n users, find the number of days on which the user traffic is maximum.

Note that all logins take place before all logouts on a single day.
### Example 
- login = [1, 2, 3]
- logout = [10, 8, 4]
- User Traffic: 0 1 2 3 3 2 2 2 2 1 1 0

The maximum user traffic is 3, which occurs on 2 days: day 3 and day 4. The answer is 2.

### Function Description
Complete the function maximum User Traffic in the editor below.
- maximumUserTraffic has the following parameter(s):
- int login[n]: an array of integers with login[i] denoting the login day of ith user.
- int logout[n]: an array of integers with logout[i] denoting the logout day of ith user

### Returns:
user int: the number of days having maximum user traffic

### Constraints
- 0 $ \leq$ n $\leq 10^5$
- 0 $ \leq$ login[i], logout[i] $\leq 10^5$
- login[i] $\leq$ logout[i]

### Solution
```python
def maximumUserTraffic(login, logout):
    n = max(max(login), max(logout))
    traffic_arr = [0] * (n + 1)
    for login_day in login:
        traffic_arr[login_day] += 1
    for logout_day in logout:
        traffic_arr[logout_day] -= 1
    accumulated_traffic = [traffic_arr[0]]
    for i in range(1, n + 1):
        accumulated_traffic.append(accumulated_traffic[-1] + traffic_arr[i])
    max_traffic = max(accumulated_traffic)
    return accumulated_traffic.count(max_traffic)
```