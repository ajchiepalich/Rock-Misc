# SMS Conversation Person Context Card

## Overview

This Lava component enhances the Rock RMS SMS Conversations experience by displaying contextual information about the selected person directly within the conversation view.

The goal is to help staff quickly understand who they are texting without navigating away from the conversation.

---

## Features

### Compact Mobile-Friendly Header

Displays:

* Person Name (linked to profile)
* Gender Initial
* Age
* Expand / Collapse control

Example:

```
Jamarius Allen   M · 29   >
```

The header is intentionally compact to prevent layout issues on smaller screens and mobile devices.

---

### Expanded Person Card

When expanded, the card displays:

#### Campus

Displays the person's primary campus.

Example:

```
Woodlawn Campus
```

---

#### Demographics

Displays:

* Gender
* Age

Example:

```
Male, 29
```

---

#### Connection Status

Displays available status badges such as:

* Member
* Visitor
* Attendee
* Single
* Married

Badges are automatically generated from the person's profile data.

---

#### Quick Actions

Provides direct access to:

##### Email

Launches the user's default mail application.

##### Phone

Launches the device dialer.

##### Flags

Displays active alert notes configured in Rock.

Supported flag types:

* Red Flag
* Yellow Flag

Flag details appear in a popover when selected.

---

### Recent Steps

Displays the three most recent steps completed within Step Program ID 3.

Example:

```
Renewal
Complete · Sep 5, 2021

Renewal
Complete · Feb 9, 2020

Baptism
Complete · Apr 3, 2016
```

Steps are ordered by most recent completion date.

---

### Record Creation Date

Displays the date the person record was first created.

Example:

```
Record Created Oct 27, 2014
```

---

## Data Sources

### Person Object

Uses standard Rock Person properties:

* Person.Id
* Person.FullName
* Person.Gender
* Person.Age
* Person.Email
* Person.PhoneNumbers
* Person.PrimaryCampus
* Person.Campus
* Person.ConnectionStatusValue
* Person.MaritalStatusValue
* Person.CreatedDateTime

---

### Flag Query

Queries Rock Notes:

```sql
Red Flag
Yellow Flag
```

Requirements:

* IsAlert = 1
* Note contains text
* Attached to current Person

---

### Recent Steps Query

Queries:

```sql
Step
StepType
StepProgram
StepStatus
PersonAlias
```

Current configuration:

```sql
StepProgramId = 3
```

Returns:

* Step Name
* Status
* Completion Date

Limited to:

```sql
TOP 3
```

most recent records.

---

## Mobile Optimization

Several adjustments were implemented specifically for the SMS Conversations mobile interface:

### Header Compression

The original implementation displayed:

```
Jamarius Allen - Male, 29
```

This caused wrapping issues on smaller screen sizes.

The current implementation uses:

```
Jamarius Allen   M · 29
```

which significantly reduces width requirements.

---

### Responsive Name Truncation

Long names automatically truncate:

```
Christopher Jo...
```

instead of wrapping onto multiple lines.

---

### Responsive Card Width

The expanded card scales based on viewport width.

Breakpoints:

| Width  | Behavior                                 |
| ------ | ---------------------------------------- |
| >480px | Full card                                |
| ≤480px | Reduced spacing and typography           |
| ≤360px | Aggressive truncation and compact layout |

---

## Accessibility

Includes:

* ARIA labels on email and phone actions
* Keyboard support
* Escape key closes active flag popovers
* Semantic `<details>` and `<summary>` elements

---

## JavaScript Behavior

### Flag Popovers

The component includes lightweight JavaScript to:

* Open flag details
* Close other open flags
* Close all flags when clicking elsewhere
* Close flags using Escape key

Only one flag popover can be open at a time.

---

## Performance Notes

The component was designed for high-volume SMS inboxes.

Optimizations include:

* Limited SQL result sets
* Minimal JavaScript
* No external dependencies
* Single event delegation pattern
* Mobile-first rendering

---

## Future Enhancements

Potential additions:

* Attendance trend summary
* Last service attended
* Small Group participation
* Volunteer team involvement
* Baptism status indicator
* Decision history
* Prayer request history
* Follow-up assignment status
* AI-generated conversation context summary

---

## Author

Church of the Highlands
Digital Team

Designed for use within the Rock RMS SMS Conversations experience.
