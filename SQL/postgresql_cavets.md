# PostgreSQL Cavets

1. ILIKE for case-insensitive match not LIKE
2. Does not use indices for where clauses in which ILIKE or LIKE are used. Only possible if you are not using bound parameters(?).
