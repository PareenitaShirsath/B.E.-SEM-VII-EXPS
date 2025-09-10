# Experiment 3 – To Install and Configure MongoDB/ Cassandra/ HBase/ Hypertable to Execute NoSQL Commands  

## Aim  
To install MongoDB and run commands.  

## Objective  
To install MongoDB and learn the commands.  

## Outcome  
Students should be able to install MongoDB on Ubuntu or Windows and learn some basic commands.  

---

## Theory  

**MongoDB** is a NoSQL database that stores data in flexible, JSON-like documents instead of traditional tables with rows and columns.  
It is designed to handle large amounts of diverse and rapidly changing data, making it popular for modern applications that require **scalability** and **flexibility**.  

Unlike relational databases, MongoDB does not require a fixed schema, so different types of data can be stored in the same collection.  
It is widely used in **web apps, big data, real-time analytics, and other scenarios** where speed and flexibility are important.  

### Key Theoretical Concepts  

1. **Document Model**  
   - MongoDB stores data in flexible JSON-like documents, called **BSON** (Binary JSON).  
   - Schema-less design allows dynamic and evolving data structures.  
   - Supports nested documents and arrays to represent hierarchical data.  

2. **Collections**  
   - Documents are grouped into **collections** (similar to tables in RDBMS).  
   - Collections do not enforce a schema, so documents may vary in structure.  

3. **Horizontal Scalability (Sharding)**  
   - MongoDB achieves scalability through **sharding**, i.e., distributing data across multiple servers.  
   - Enables handling of large datasets and high traffic loads.  

4. **Replication (Replica Sets)**  
   - MongoDB supports **replica sets** for high availability and redundancy.  
   - A replica set includes one primary (handles writes) and multiple secondaries (replicas).  

5. **CAP Theorem Consideration**  
   - MongoDB prioritizes **Availability** and **Partition Tolerance**.  
   - Provides **eventual consistency** with configurable consistency levels.  

6. **Flexible Schema**  
   - Schema-less nature allows adapting to changing requirements.  
   - Avoids costly schema migrations required in relational databases.  

7. **Atomicity at Document Level**  
   - Operations on a single document are **atomic** (all-or-nothing).  
   - Prevents partial updates and ensures integrity.  

---

## Installing MongoDB  

### Step 1: Download MongoDB  
- Open Google and search **MongoDB**.  
- Visit the official website.  
- Navigate to **Products → Community Edition → Download Package**.  
- Download the `.msi` installer file.  

⚠️ During installation, **uncheck MongoDB Compass** (GUI installer).  

---

### Step 2: Configure Path  
- After installation, go to:  
  `C:/Program Files/MongoDB/Server/8.0/bin`  
- Copy the path.  
- Open **Edit the System Environment Variables** → **Environment Variables**.  
- Add the copied path to the system `PATH` variable.  

---

### Step 3: Install MongoDB Shell  
- Search for **MongoDB Shell (mongosh)** in Google.  
- Download the `.msi` package and install it.  
- During installation, allow access permissions for all users.  
- Add its path to system environment variables as done for MongoDB.  

---

### Step 4: Verify Installation  
- Open **Command Prompt** and type:  
  ```bash
  mongod --version
