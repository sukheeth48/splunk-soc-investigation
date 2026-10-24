# SOC Authentication Investigation Dashboard

## Purpose

Visualize authentication activity from the imported synthetic CSV dataset and support initial triage of suspicious login patterns.

## Dashboard Panels

### 1. Login Outcomes

**SPL:**

```spl
index=* sourcetype=csv
| stats count BY event_action
```

**Purpose:** Compares failed and successful authentication events.

**Expected sample result:** Three failures and one success.

### 2. Failed Logins by Username

**SPL:**

```spl
index=* sourcetype=csv event_action="failure"
| stats count AS failed_attempts BY username
| sort - failed_attempts
```

**Purpose:** Ranks usernames by the number of failed login attempts.

### 3. Login Activity Over Time

**SPL:**

```spl
index=* sourcetype=csv
| timechart span=1m count BY event_action
```

**Purpose:** Displays authentication events across time buckets to help identify bursts of activity.

## Dataset Limitations

The current dataset contains four synthetic records for one username and one documentation-reserved IP address. It does not represent a real attack or production authentication environment.

## Operational Considerations

- Confirm the selected time range before interpreting dashboard results.
- Validate event timestamps and field extractions.
- Restrict access to sensitive production logs.
- Test detection logic against a larger dataset before using it operationally.
