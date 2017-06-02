---
title: "指定入口点 | Microsoft Docs"
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
  - "平台调用中的特性字段, EntryPoint"
  - "EntryPoint 字段"
  - "平台调用, 特性字段"
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 指定入口点
入口点用于标识函数在 DLL 中的位置。  在托管对象中，目标函数的原名或序号入口点将标识跨越交互操作边界的函数。  此外，您可以将入口点映射到一个不同的名称，这实际上是将函数重命名。  
  
 以下列出了重命名 DLL 函数的可能原因：  
  
-   避免使用区分大小写的 API 函数名  
  
-   符合现行的命名标准  
  
-   提供采用不同数据类型的函数（通过声明同一 DLL 函数的多个版本）  
  
-   简化对包含 ANSI 和 Unicode 版本的 API 的使用  
  
 本主题将说明如何在托管代码中重命名 DLL 函数。  
  
## 在 Visual Basic 中重命名函数  
 Visual Basic 在 **Declare** 语句中使用 **Function** 关键字来设置 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=fullName> 字段。  下面的示例显示了一个基本的声明。  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
 如下例所示，通过在定义中包括 **Alias** 关键字，可以用 **MsgBox** 替换 **MessageBox** 入口点。  在这两个示例中，**Auto** 关键字使您无需指定入口点的字符集版本。  有关选择字符集的更多信息，请参见[指定字符集](../../../docs/framework/interop/specifying-a-character-set.md)。  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MsgBox Lib "user32.dll" _  
       Alias "MessageBox" (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## 在 C\# 和 C\+\+ 中重命名函数  
 可以使用 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=fullName> 字段通过名称或序号指定 DLL 函数。  如果函数在方法定义中的名称与入口点在 DLL 的名称相同，则不必用 **EntryPoint** 字段来显式地标识函数。  否则，使用以下特性形式之一来指示名称或序号：  
  
```  
[DllImport("dllname", EntryPoint="Functionname")]  
[DllImport("dllname", EntryPoint="#123")]  
```  
  
 请注意，序号前必须带有井号 \(\#\)。  
  
 下面的示例演示如何使用 **EntryPoint** 字段将代码中的 **MessageBoxA** 替换为 **MsgBox**。  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
    [DllImport("user32.dll", EntryPoint="MessageBoxA")]  
    public static extern int MsgBox(int hWnd, String text, String caption,  
                                    uint type);  
}  
  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", EntryPoint="MessageBoxA")]  
extern "C" int MsgBox(HWND hWnd,  
                      String*  pText,  
                      String*  pCaption,  
                      unsigned int uType);  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [平台调用示例](../../../docs/framework/interop/platform-invoke-examples.md)   
 [用平台调用封送数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)