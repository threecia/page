# LLVM study notes
---
## attribute語法
attribute本身以這種形式出現: `__attribute__((name1, name2(arg1, arg2, arg3), name3))`

`__attribute__((noreturn))`: noreturn 的用意是標記 callee function 沒有 return 動作, 這個attribute較常被 compiler 設計成警告 noreturn 之後的 user code

`__attribute__((disable_tail_calls))`: disable_tail_calls 的用意是當callee return statement是一個function call, 會直接省略當下的callee到caller之間的return value read-write 動作

[reference](https://gcc.gnu.org/onlinedocs/gcc-4.9.1/gcc/Attribute-Syntax.html#Attribute-Syntax)