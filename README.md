# postgres_tuning_optimizations

In this article, I discuss about usage of postgres docker service with optimal RAM allocation, CPU consumption and query read performance.
I will also mention about the methodologies used to use minimal RAM.

1) Reduce number of connections that are required for read & write
- Link about work_mem, maintanance_mem & autovaccum_mem, max_connections in configurations
- How does reducing number of connection contribue to less RAM (shared_memory & work_mem)
- How to reduce number of connections (Bulk writes. Trying to utilize one connection wherever applicable)

2) Postgres partitioning
- Create multiple tables which enables faster data read for each device or per day based on scenario.

3) Table structuring & Query modelling
- Consider to use integers wherever u require conditional query reads.
- consider to use accurate and good queries (GROUPBY & HAVING)
- use indexing

4) Data read in chunks. Instead of reading complete data, read data in chunks aggregate it and store.

5) autovaccum can cause severe delay if it is invoked again and again. Hence be clear about the usage, if it is explicitly triggered.

