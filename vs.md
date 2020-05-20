## Visual Studio Tips
---

### 注意事項
 - 在VS2019使用toolset v141_xp 產生的libray會有幾個問題  
  1. 錯誤`... error LNK2019: unresolved external symbol __imp____stdio_common_vsprintf referenced in function __vsnprintf_l`  
     這是因為從VS2015開始, snprintf在宣告中加入inline的attribute, 因此compiler會產生inline function name並在連結的時候發生找不到symbol的錯誤, 可以藉由macro `_NO_CRT_STDIO_INLINE` 取消inline動作, 解決這個問題  
     [參考來源](https://stackoverflow.com/questions/32740172/unresolved-stdio-common-vsprintf-s-what-library-has-this)  
  2. 沒有`snprintf`, 要使用`_snprintf` (多一個底線的版本)不然會unresolved external symbol  
