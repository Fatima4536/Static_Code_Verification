# Code Review

| Line Number | Defect Type | Why It Is a Problem | Severity |
|---|---|---|---|
| 41 | Array Overflow | Adding a monster beyond the array capacity can cause out-of-bounds memory access. | High |
| 47 | Assignment Instead of Comparison | Using `=` instead of `==` changes the monster ID and may return the wrong monster. | High |
| 54 | Null Pointer Dereference | If the monster is not found, `m` is `nullptr`, and accessing its members can crash the program. | High |
| 56 | Incorrect Arithmetic / Type Handling | `dmg` is unsigned, so comparing the health calculation with zero may not work as intended. | Medium |
| 64 | Loop Boundary Error | Using `i <= monsterCount` accesses an invalid array element. | High |
| 72 | Returning Reference to Local Variable | Returning `label` by reference creates a dangling reference because the local variable is destroyed when the function returns. | High |
| 77 | Uninitialized Variable | `sum` is not initialized before arithmetic, producing an unpredictable result. | Medium |
| 78–79 | Uninitialized Arithmetic | Adding attack values to an uninitialized `sum` leads to an incorrect average. | Medium |
| 79 | Division by Zero | If `monsterCount` is zero, dividing by it causes undefined behavior. | High |
| 85–86 | Use After Free | Accessing `m->name` after deleting `m` causes undefined behavior. | High |
| 94–98 | Missing Return Statement | `playerRank()` does not return a value when the score is 100 or below. | Medium |
| 102 | Buffer Overflow Risk | A fixed-size character buffer may overflow if the user enters a long boss name. | High |
| 105 | Unsafe Input | Reading a name into a fixed-size character buffer without a width limit can overwrite memory. | High |
| 109 | Incorrect Memory Deallocation | Using `delete` instead of `delete[]` for an array allocated with `new[]` causes undefined behavior. | High |
| 119 | Array Overflow | Six monsters are spawned, but the array capacity is only five. | High |
| 121 | Memory Leak | The dynamically allocated `bonus` monster is never deleted. | Medium |
| 123 | Null Pointer Dereference | Attacking nonexistent monster ID 99 can cause a crash because `attackMonster()` does not check `m`. | High |
| 124 | Null Pointer Dereference | If the requested monster is not found, `getMonsterLabel()` dereferences a null pointer. | High |
| 130 | Object Lifetime Error | Deleting a monster does not remove its pointer from the array or update `monsterCount`, leaving a dangling pointer. | High |
| 133 | Shallow Copy | Copying `Game` duplicates raw pointers, potentially causing double deletion when both objects are destroyed. | High |

