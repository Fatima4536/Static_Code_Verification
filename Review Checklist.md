| Category | Result | Defect |
|---|---|---|
| Initialization | Fail | Uninitialized variable `sum` in `averageAttack()` |
| Pointers / Arrays / Buffers | Fail | Array overflow risk, incorrect assignment in `findMonster()`, and memory management issues |
| Loops | Fail | Incorrect loop condition `i <= monsterCount` causes out-of-bounds access |
| Arithmetic | Fail | Incorrect unsigned comparison in `attackMonster()` and integer division in `calculateDamage()` |
| Control Flow | Fail | Missing return statement in `playerRank()` when score is 100 or below |
| Function Calls | Fail | Missing null pointer checks in `attackMonster()` and `getMonsterLabel()` |
| Classes | Fail | Shallow copying of `Game` causes double deletion; `defeatMonster()` accesses deleted memory |
