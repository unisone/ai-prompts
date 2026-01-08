# SQL Query Builder

## Description

Generates SQL queries from natural language with proper formatting, optimization hints, and safety checks.

## When to Use

- Writing complex queries from requirements
- Optimizing slow queries
- Learning SQL patterns
- Quick data exploration

## Prompt

```
Generate a SQL query for: [NATURAL LANGUAGE REQUEST]

<schema>
[Paste relevant table schemas here, or describe structure]
</schema>

<requirements>
- Database: [PostgreSQL/MySQL/SQLite/BigQuery/etc]
- Include comments explaining logic
- Format for readability
- Flag any assumptions made
- Note potential performance concerns
</requirements>

<output_format>
## Query

```sql
-- [Your formatted query with comments]
```

## Explanation
[Step-by-step explanation of what each part does]

## Assumptions
[Any assumptions made about schema or requirements]

## Performance Notes
[Indexes needed, potential bottlenecks, optimization tips]

## Safety Checks
[Any risks: missing WHERE clause, full table scan, etc]
</output_format>
```

## Why It Works

1. **Schema context**: AI can't guess your table structure
2. **DB-specific syntax**: PostgreSQL != MySQL
3. **Explanation included**: Understand, don't just copy-paste
4. **Safety checks**: Catches dangerous queries before execution

## Example

Input:
```
Generate SQL for: Find users who signed up in the last 30 days, 
made at least 2 purchases, and haven't logged in for 7 days.

Schema:
- users (id, email, created_at, last_login_at)
- purchases (id, user_id, amount, created_at)

Database: PostgreSQL
```

Output:
```sql
-- Users: signed up last 30d, 2+ purchases, inactive 7d
SELECT 
    u.id,
    u.email,
    u.created_at AS signup_date,
    u.last_login_at,
    COUNT(p.id) AS purchase_count
FROM users u
INNER JOIN purchases p ON p.user_id = u.id
WHERE 
    u.created_at >= NOW() - INTERVAL '30 days'
    AND u.last_login_at < NOW() - INTERVAL '7 days'
GROUP BY u.id, u.email, u.created_at, u.last_login_at
HAVING COUNT(p.id) >= 2
ORDER BY u.created_at DESC;

-- Performance: Add index on users(created_at, last_login_at)
-- and purchases(user_id) if not present
```

## Query Optimization Mode

```
Optimize this SQL query:
[Paste slow query]

Explain:
1. What makes it slow (likely causes)
2. The optimized version
3. What indexes would help
4. EXPLAIN ANALYZE interpretation (if provided)
```

## Quick Mode

For simple queries:
```
[DB type] query: [natural language description]
Schema: [tables and key columns]
```

Example: "PostgreSQL query: count orders by status this month. Schema: orders(id, status, created_at)"

## Notes

- Always test on non-production first
- EXPLAIN ANALYZE your queries
- Be careful with JOINs on large tables
- Add LIMIT when exploring data
