### ViDbgOutputBuffer

Windows应用程序开发过程中常会使用 **AppVerify** 检测程序中的潜在Bug，在发现有Bug时会及时生成dump文件。通过Windbg调试器对生成的Dump文件进行分析可定位到Bug原因，特别是 **AppVerify** 给到的错误描述信息对定位Bug非常有用。

Dump分析命令 **!analyze -v** 会输出详细的错误描述信息
![analyze -v](../../windbg-analyze-v.png)

也可以使用以下命令输出错误描述信息。
>**da vrfcore!ViDbgOutputBuffer**

![da vrfcore!ViDbgOutputBuffer](../../windbg-da-vidbgoutputbuffer.png)
