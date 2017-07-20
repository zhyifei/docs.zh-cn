---
title: "传递结构 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "平台调用, 调用非托管函数"
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 传递结构
许多非托管函数需要您将结构（Visual Basic 中的用户定义类型）的成员或在托管代码中定义的类成员作为参数传递给函数。  在使用平台调用将结构或类传递到非托管代码时，必须提供用来保留原始布局和对齐方式的附加信息。  本主题介绍 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 特性，它用于定义格式化类型。  对于托管结构和类，您可以从 **LayoutKind** 枚举提供的若干可预知的布局行为中进行选择。  
  
 本主题中提供的概念的核心是结构类型和类类型之间的重要区别。  结构是值类型，类是引用类型 \- 类始终提供至少一级内存间接寻址（指向某一值的指针）。  因为非托管函数经常要求间接寻址，所以这一区别是十分重要的，如下表中第一列的签名所示。  其余列中的托管结构和类声明显示在声明中可以调整的间接寻址级别的程度。  说明向 Visual Basic 和 Visual C\# 提供。  
  
|非托管签名|托管声明：               <br /> 没有间接寻址               <br />  `Structure MyType`  <br />  `struct MyType;`|托管声明：               <br /> 一级间接寻址               <br />  `Class MyType`  <br />  `class MyType;`|  
|-----------|----------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> 要求零级间接寻址。|`DoWork(ByVal x As MyType)`  <br />  `DoWork(MyType x)`<br /><br /> 增加零级间接寻址。|不可能，因为已有一级间接寻址。|  
|`DoWork(MyType* x);`<br /><br /> 要求一级间接寻址。|`DoWork(ByRef x As MyType)`  <br />  `DoWork(ref MyType x)`<br /><br /> 增加一级间接寻址。|`DoWork(ByVal x As MyType)`  <br />  `DoWork(MyType x)`<br /><br /> 增加零级间接寻址。|  
|`DoWork(MyType** x);`<br /><br /> 要求二级间接寻址。|不可能，因为不能使用 **ByRef** **ByRef**或者`ref` `ref`不能被使用。|`DoWork(ByRef x As MyType)`  <br />  `DoWork(ref MyType x)`<br /><br /> 增加一级间接寻址。|  
  
 该表描述用于平台调用声明的以下原则：  
  
-   在非托管函数不要求任何间接寻址时使用按值传递的结构。  
  
-   在非托管函数要求一级间接寻址时使用按引用传递或按类传递的结构。  
  
-   在非托管函数要求二级间接寻址时使用按引用传递的类。  
  
## 声明和传递结构  
 下面的示例将显示如何在托管代码中定义 `Point` 和 `Rect` 结构，并将这些类型作为参数传递给 User32.dll 文件中的 **PtInRect** 函数。  **PtInRect** 具有以下非托管签名：  
  
```  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 请注意，由于函数需要指向 RECT 类型的指针，必须通过引用来传递 Rect 结构。  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
    Public x As Integer  
    Public y As Integer  
End Structure  
  
Public Structure <StructLayout(LayoutKind.Explicit)> Rect  
    <FieldOffset(0)> Public left As Integer  
    <FieldOffset(4)> Public top As Integer  
    <FieldOffset(8)> Public right As Integer  
    <FieldOffset(12)> Public bottom As Integer  
End Structure  
  
Class Win32API      
    Declare Auto Function PtInRect Lib "user32.dll" _  
    (ByRef r As Rect, p As Point) As Boolean  
End Class  
  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
    public int x;  
    public int y;  
}     
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
    [FieldOffset(0)] public int left;  
    [FieldOffset(4)] public int top;  
    [FieldOffset(8)] public int right;  
    [FieldOffset(12)] public int bottom;  
}     
  
class Win32API {  
    [DllImport("User32.dll")]  
    public static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## 声明和传递类  
 只要类具有固定的成员布局，就可以将类的成员传递给非托管的 DLL 函数。  下面的示例将说明如何将 `MySystemTime` 类的成员（按连续的顺序定义）传递给 User32.dll 文件中的 **GetSystemTime**。  **GetSystemTime** 具有以下非托管签名：  
  
```  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 与值类型不同，类始终具有至少一级间接寻址。  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
Imports Microsoft.VisualBasic  
  
<StructLayout(LayoutKind.Sequential)> Public Class MySystemTime  
    Public wYear As Short  
    Public wMonth As Short  
    Public wDayOfWeek As Short   
    Public wDay As Short  
    Public wHour As Short  
    Public wMinute As Short  
    Public wSecond As Short  
    Public wMiliseconds As Short  
End Class  
  
Public Class Win32  
    Declare Auto Sub GetSystemTime Lib "Kernel32.dll"(sysTime _  
        As MySystemTime)  
    Declare Auto Function MessageBox Lib "User32.dll"(hWnd As IntPtr, _  
        txt As String, caption As String, Typ As Integer) As Integer  
End Class  
  
Public Class TestPlatformInvoke      
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        Win32.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        Win32.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)        
    End Sub  
End Class  
  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class MySystemTime {  
    public ushort wYear;   
    public ushort wMonth;  
    public ushort wDayOfWeek;   
    public ushort wDay;   
    public ushort wHour;   
    public ushort wMinute;   
    public ushort wSecond;   
    public ushort wMilliseconds;   
}  
class Win32API {  
    [DllImport("Kernel32.dll")]  
    public static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern int MessageBox(IntPtr hWnd,  
         string text, string caption, int options);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        Win32API.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        Win32API.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## 请参阅  
 [调用 DLL 函数](../../../docs/framework/interop/calling-a-dll-function.md)   
 [StructLayoutAttribute 类](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic)   
 [StructLayoutAttribute 类](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic)   
 [FieldOffsetAttribute 类](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic)