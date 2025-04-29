## Git Basics
___
- Git is a distributed version control system.
- Version Control History
	1. Revision Control System  (RCS) -
		- They just used to store the difference between the two files
		- Based on the differences the system was able to build the previous file.
		- Issues - local system based, single point of contact, hard to collaborate
	2. Centralized Version Control System (CVCs) -
		- All files changes were stored in a single place rather than a local machine
		- Here we check just the latest snapshot of the files
		- Network Latency
		- Issues - single point of contact, only allowed to collaborate on the latest changes are versions.
		- If the central repo was corrupted, then we would lose all history.
	3. Distributed Version Control System (DVCs) -
		- Full repository is mirrored, including full history and not only just the latest snapshot.
		- So if any server dies, all the data can be recovered and copied back easily
		- High Speed, as it runs locally.

## How is Git Different ?
___
1. Git servers as a mini filesystem
2. All other VCs stored data as file based changes (delta-based version control)
	- Example A - File A changed to A1, then they used to store Delta between A1 and A
	- If we changed that A1 to A2, the used to store only the delta between A2 and A1

| Others                                                     | Git                                                                                                                                                    |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Version 1 : "Hello World"<br>Version 2 : "Hello New World" | Version 1 : "Hello World"<br>Version 2 : "Hello New World"                                                                                             |
| Change (Delta) = Insert New at position 6                  | Version 1 : Stored completely<br>Version 2 : Stored completely                                                                                         |
| Original Version  + Delta = New Version                    | Now a pointer points to Version 2 post commit, <br>So at every commit we have the full project replicated (git has its optimizations and compressions) |
