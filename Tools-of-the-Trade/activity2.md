# Apply Filters to SQL Queries

## Project Description

In this project, I used SQL filtering techniques to investigate potential security incidents and retrieve employee information from organizational databases. I applied operators such as AND, OR, NOT, and LIKE to filter records based on dates, times, locations, and departments. These queries helped identify suspicious login activity and determine which employee systems required security updates.

---

## Retrieve After Hours Failed Login Attempts

To identify failed login attempts that occurred after business hours, I queried the `log_in_attempts` table and filtered for failed logins after 18:00.

```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00'
AND success = 0;
```

This query returns all records where the login attempt occurred after 6:00 PM and the login was unsuccessful.

---

## Retrieve Login Attempts on Specific Dates

To investigate suspicious activity, I retrieved all login attempts that occurred on May 8 and May 9, 2022.

```sql
SELECT *
FROM log_in_attempts
WHERE login_date = '2022-05-08'
OR login_date = '2022-05-09';
```

This query uses the OR operator to return login attempts from either date.

---

## Retrieve Login Attempts Outside of Mexico

To investigate activity that did not originate from Mexico, I filtered out all records where the country was Mexico.

```sql
SELECT *
FROM log_in_attempts
WHERE NOT country LIKE 'MEX%';
```

The LIKE operator with `%` matches both `MEX` and `MEXICO`. The NOT operator excludes those records and returns login attempts from all other countries.

---

## Retrieve Employees in Marketing

To identify Marketing employees located in the East building, I queried the employees table using both department and office filters.

```sql
SELECT *
FROM employees
WHERE department = 'Marketing'
AND office LIKE 'East%';
```

The AND operator ensures both conditions are met, while LIKE identifies offices that begin with "East".

---

## Retrieve Employees in Finance or Sales

To identify employees whose machines require a security update, I queried employees in the Finance and Sales departments.

```sql
SELECT *
FROM employees
WHERE department = 'Finance'
OR department = 'Sales';
```

This query returns employees from either department using the OR operator.

---

## Retrieve All Employees Not in IT

To identify employees who still needed an update, I excluded those in the Information Technology department.

```sql
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```

This query uses the NOT operator to return employees from every department except Information Technology.

---

## Summary

In this project, I used SQL filtering techniques to investigate login activity and identify employee groups requiring security updates. I applied AND, OR, NOT, and LIKE operators to narrow search results based on specific conditions. These queries demonstrate how SQL can be used to analyze security events, investigate suspicious activity, and support organizational security operations.
