# 1. Aurora DB ☁️

- Started in 2014
- Aws is owner
- Mysql compatible
- 5x faster than mysql and 3x faster than postgres
- 10x cheaper
- 10GB default
- Auto-scaling with 64Gb default
- Maximum 64TB
- It is possible to create until 15 replica
  - The **main process** handles database **writing** and each **replica** handles **reading**
  - You can configure to many applications read the database using some replica without affecting the main process of the database
- Recover: point in-time
- Continuous backup: until 3 zones
- Free tier is not available