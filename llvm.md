# LLVM study notes
---
## Tip
萬用breakpoint  
 - [clang::Diagnostic::FormatDiagnostic](file:///d:\app_toolchain_unsp_hq\src\exeproject\qpcx\src\tools\clang\lib\basic\diagnostic.cpp), Line 763  
 - [{}::CodeGeneratorImpl::HandleTranslationUnit](file:///d:\app_toolchain_unsp_hq\src\exeproject\qpcx\src\tools\clang\lib\codegen\modulebuilder.cpp), Line 255  
 - [clang::ASTContext::Allocate](file:///d:\app_toolchain_unsp_hq\src\exeproject\qpcx\src\tools\clang\include\clang\ast\astcontext.h), Line 673  

## Info
 - Parser的開始點 [clang::Parser::ParseTopLevelDecl](file:///d:\app_toolchain_unsp_hq\src\exeproject\qpcx\src\tools\clang\lib\parse\parser.cpp), Line 682  
 - `__attribute((...))` GNU attribute handler: [clang::Parser::ParseGNUAttributes](file:///d:\app_toolchain_unsp_hq\src\exeproject\qpcx\src\tools\clang\lib\parse\parsedecl.cpp), Line 150  

## materials
1. [Clang 11 Documantation](https://clang.llvm.org/docs/AttributeReference.html)  
2. [How-to-add an attribute](http://clang.llvm.org/docs/InternalsManual.html#how-to-add-an-attribute)  
3. [[llvm-dev] Adding a function attribute with an argument](http://lists.llvm.org/pipermail/llvm-dev/2015-October/091122.html)  

## attribute語法
attribute本身以這種形式出現: `__attribute__((name1, name2(arg1, arg2, arg3), name3))`

`__attribute__((noreturn))`: noreturn 的用意是標記 callee function 沒有 return 動作, 這個attribute較常被 compiler 設計成警告 noreturn 之後的 user code  
`__attribute__((disable_tail_calls))`: disable_tail_calls 的用意是當callee return statement是一個function call, 會直接省略當下的callee到caller之間的return value read-write 動作  

## 新增language extension
 - `include/clang/Basic/LangOptions.def`新增

## llc不支援LLVM-IR to C 的轉換
從LLVM 3.1開始[拿掉了](https://releases.llvm.org/3.1/docs/ReleaseNotes.html)"LLVM_TARGETS_TO_BUILD=CBackend"的選項, 因此大家只能各顯神通產生source code  
理由: The C backend has been removed. It had numerous problems, to the point of not being able to compile any nontrivial program.

[reference](https://gcc.gnu.org/onlinedocs/gcc-4.9.1/gcc/Attribute-Syntax.html#Attribute-Syntax)
