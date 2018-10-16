Distributed Class Management System (DCMS) using Java RMI

Distributed Class Management System: a distributed system used by center managers to manage information regarding the teachers and students across different centers.
Consider three centers locations: Montreal (MTL), Laval (LVL) and Dollard-des-Ormeaux (DDO) for your implementation. The server for each center (called CenterServer) must maintain a number of Records. There are two types of Records: TeacherRecord and StudentRecord. A Record can be identified by a unique RecordID starting with TR (for TeacherRecord) or SR (for StudentRecord) and ending with a 5 digits number (e.g. TR10000 for a TeacherRecord or SR10001 for a StudentRecord).

The Records are placed in several lists that are stored in a hash map according to the first letter of the last name indicated in the records. For example, all the Records with the last name starting with an “A” will belong to the same list and will be stored in a hash map (acting as the database) and the key will be “A”. We do not distinguish between teacher records and Student records when inserting them into the hash map (i.e. a list may contain both teacher and Student records). Each server also maintains a log containing the history of all the operations that have been performed on that server. This should be an external text file (one per server) and shall provide as much information as possible about what operations are performed, at what time and who performed the operation.

The users of the system are center managers. They can be identified by a unique managerID, which is constructed from the acronym of the center and a 4-digit number (e.g. MTL1111). Whenever a manager performs an operation, the system must identify the center that manager belongs to by looking at the managerID prefix and perform the operation on that server. The managers carry with them a log (text file) of the actions they performed on the system and the response from the system when available. For example, if you have 10 managers using your system, you should have a folder containing 10 logs.

The operations that can be performed are the following:

1) createTRecord (firstName, lastName, address, phone, specialization, location)

2) createSRecord (firstName, lastName, courseRegistered, status, statusDate)

3) getRecordCounts ()

4) editRecord (recordID, fieldName, newValue)

In this assignment, you are going to develop this application using Java RMI. Specifically, do the following:
1) Write the Java RMI interface definition for the CenterServer with the specified operations.
2) Implement the CenterServer.
3) Design and implement a ManagerClient, which invokes the center’s server system to test the correct operation of the DCMS invoking multiple CenterServer (each of the servers initially has a few records) and multiple managers.

You should design the CenterServer maximizing concurrency. In other words, use proper synchronization that allows multiple police manager to perform operations for the same or different records at the same time.
