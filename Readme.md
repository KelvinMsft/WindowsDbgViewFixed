# Introduction

Binary fix for Windows 10 Sysinternal tools - Dbgview

When execute dbgview twice and viewing the kernel log, it shows below error :

<img src ="https://user-images.githubusercontent.com/22551808/35961635-46895884-0ce9-11e8-8ca7-b00a9c6c530e.png" > </img>

This repo fix for it. and doesn't repsonsible for any maintanence.

# The cause:

1. First, Dbgview.exe releases a Dbgv.sys and start it  

2. if start it successfully, it will delete a dbgv.sys

3. Second, DbgView is terminated and Created again (twice),  and release it driver too, AND overwrite it.

4. There is a reason that , when the first step loaded the Dbgv.sys, the corresponding file is not premitted to modify and delete.

5. If overwrite it fail. It pop the dialog as above screen capture.
 
 
# Solution :
1. Rewrite the result overwriting the Dbgv.sys for windows 10.
