# Pay Tracker

Simple single file html & js static tracker for recurring income (`money_in`) and expenses (`money_out`).

![Pay Tracker example](./example.png)

## Data Structure

Both `money_in` and `money_out` are arrays of objects.

Each object uses this base shape:

```js
{
  name: "Label shown in table/calendar",
  amount: 600,
  baseDate: "27/03/24", // DD/MM/YY or DD/MM/YYYY
  type: "fixed_period" | "calendar_date"
}
```

### Type: `fixed_period`

Use this for events that repeat every _N_ days.

Required extra field:

```js
periodDays: 14
```

Example:

```js
{ name: "Job1", amount: 600, baseDate: "27/03/24", type: "fixed_period", periodDays: 14 }
```

### Type: `calendar_date`

Use this for events that repeat monthly on a calendar day.

Required extra field:

```js
calendarDay: 28
```

Example:

```js
{ name: "Rent", amount: 450, baseDate: "01/03/24", type: "calendar_date", calendarDay: 1 }
```

## Where to Edit

Update the arrays in `index.html`:

- `money_in` for incoming money
- `money_out` for outgoing bills/expenses
