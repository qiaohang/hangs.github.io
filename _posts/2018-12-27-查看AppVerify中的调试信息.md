---
layout:     post
title:      查看AppVerify中的调试信息
subtitle:   AppVerify生成的dump分析总结
date:       2018-12-27
author:     QH
header-img:
catalog: true
tags:
    - Windbg
    - AppVerify
---

### 查看AppVerify中的调试信息

Windows应用程序开发过程中常会使用 **AppVerify** 检测程序中的潜在Bug，在发现有Bug时会及时生成dump文件。通过Windbg调试器对生成的Dump文件进行分析可定位到Bug原因，特别是 **AppVerify** 给到的错误描述信息对定位Bug非常有用，可以使用以下3种方法查看该信息。

1. Dump分析命令 **!analyze -v** 会输出详细的错误描述信息。
![analyze -v](../../windbg-analyze-v.png)

2. vrfcore中的全局变量**ViDbgOutputBuffer**可以使用以下命令输出错误描述信息。
>**da vrfcore!ViDbgOutputBuffer**
![da vrfcore!ViDbgOutputBuffer](../../windbg-da-vidbgoutputbuffer.png)

3. **AppVerify**的日志也会保存异常调试信息，日志文件可以导出保存为xml文件格式，再结合日志中的信息进行dump分析。
![appverify log](../../appverify-log.png)