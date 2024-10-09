# MongoDB `explain()` Learning Plan

## Goal: Understand how the `explain()` function works in MongoDB and how to interpret query performance.

### Week Overview:
- **Total Duration**: 7 days
- **Daily Commitment**: 1-2 hours

---

### ✅ Step 1: Introduction to MongoDB Queries and Indexing
- [x] **Task 1**: Review MongoDB queries and basic indexing concepts.
    - **Resource**: [MongoDB CRUD Operations Documentation](https://www.mongodb.com/docs/manual/crud/)
		✅ Note: [[CRUD Mongo tips]] 
    - **Resource**: [MongoDB Indexes Overview](https://www.mongodb.com/docs/manual/indexes/)
		✅ Note: [[Indexes]]
- [x] **Task 2**: Read about how indexes impact query performance.
    - **Resource**: [How Indexes Improve Query Performance](https://www.mongodb.com/docs/manual/core/indexes/#improve-query-performance)

---

### Step 2: Understanding the `explain()` Method
- [ ] **Task 1**: Study the official documentation for the `explain()` method.
    - **Resource**: [MongoDB explain() Method](https://www.mongodb.com/docs/manual/reference/method/cursor.explain/)
- [ ] **Task 2**: Read this article about how `explain()` helps in understanding MongoDB queries.
    - **Resource**: [A Guide to MongoDB explain()](https://scalegrid.io/blog/a-guide-to-mongodb-explain/)

---

### Step 3: Types of Explain Output (`queryPlanner`, `executionStats`, `allPlansExecution`)
- [ ] **Task 1**: Study the three verbosity levels of `explain()` method in depth.
    - **Resource**: [MongoDB explain() Output - Verbosity Levels](https://www.mongodb.com/docs/manual/reference/explain-results/)
- [ ] **Task 2**: Read more on understanding MongoDB’s execution plan.
    - **Resource**: [Understanding MongoDB Execution Plans](https://kb.objectrocket.com/mongo-db/how-to-understand-mongodb-execution-plans-273)
- [ ] Task 3: Conspect [lecture](https://www.youtube.com/watch?v=UMzt4PbHtm8)

---

### Step 4: Analyzing `queryPlanner` Output
- [ ] **Task 1**: Learn how to interpret the `queryPlanner` section of the explain output.
    - **Resource**: [MongoDB Query Planner Documentation](https://www.mongodb.com/docs/manual/reference/explain-results/#query-planner-output)
- [ ] **Task 2**: Dive deeper into MongoDB’s query planner and how it chooses execution plans.
    - **Resource**: [How MongoDB’s Query Planner Works](https://www.mongodb.com/blog/post/how-the-mongodb-query-planner-works)

---

### Step 5: Analyzing `executionStats` Output
- [ ] **Task 1**: Study the `executionStats` section to evaluate query performance.
    - **Resource**: [MongoDB Execution Stats Documentation](https://www.mongodb.com/docs/manual/reference/explain-results/#executionstats)
- [ ] **Task 2**: Read how to interpret execution stats for improving MongoDB queries.
    - **Resource**: [Decoding MongoDB Execution Stats](https://scalegrid.io/blog/how-to-decipher-mongodb-executionstats-explain-output/)

---

### Step 6: Optimizing Queries with Explain Output
- [ ] **Task 1**: Read about common MongoDB query optimization techniques.
    - **Resource**: [MongoDB Query Optimization Documentation](https://www.mongodb.com/docs/manual/core/query-optimization/)
- [ ] **Task 2**: Apply what you’ve learned by optimizing queries based on explain outputs.
    - **Hands-On**: Use your own MongoDB instance or a cloud-based service like MongoDB Atlas to run queries and analyze them using `explain()`. Create indexes, compare `executionStats`, and optimize.

---

### Step 7: Review and Final Practice
- [ ] **Task 1**: Review key concepts related to queries, indexes, and explain output.
    - **Resource**: [MongoDB Query Performance FAQ](https://www.mongodb.com/docs/manual/faq/query-performance/)
- [ ] **Task 2**: Practice with real-world query optimization scenarios and explore MongoDB’s performance-tuning best practices.
    - **Resource**: [MongoDB Performance Tuning Guide](https://www.mongodb.com/docs/manual/core/performance/)
    - **Resource**: [MongoDB University Performance Course](https://university.mongodb.com/courses/M201/about)

---

### Week Completion:
- [ ] Congratulations! You've mastered the MongoDB `explain()` function!
