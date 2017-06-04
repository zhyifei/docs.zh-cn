---
title: "平台调用示例 | Microsoft Docs"
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
  - "COM 互操作, 平台调用"
  - "DLL 函数"
  - "示例 [.NET Framework], 平台调用"
  - "与非托管代码间的互操作, 平台调用"
  - "平台调用, 示例"
  - "非托管函数"
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 平台调用示例
下面的示例将说明如何定义和调用 User32.dll 中的 **MessageBox** 函数，并将简单字符串当作参数进行传递。  在这些示例中，[DllImportAttribute.CharSet Field](frlrfSystemRuntimeInteropServicesDllImportAttributeClassCharSetTopic) 字段设置为 **Auto**，以便让目标平台确定字符宽度和字符串封送处理。  
  
 同一示例也会出现在 Visual Basic、C\# 和 C\+\+ 中。  若要显示所有示例，请单击页面左上角的“语言筛选器”按钮 ![](../../../docs/framework/interop/media/filter2.gif "Filter2")。  有关其他示例，请参见[用平台调用封送数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)。  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
       ByVal caption As String, ByVal Typ As Integer) As IntPtr  
End Class  
  
Public Class HelloWorld      
    Public Shared Sub Main()  
        Win32.MessageBox(0, "Hello World", "Platform Invoke Sample", 0)  
    End Sub  
End Class  
  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
     [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern IntPtr MessageBox(int hWnd, String text,   
                     String caption, uint type);  
}  
  
public class HelloWorld {  
    public static void Main() {  
       Win32.MessageBox(0, "Hello World", "Platform Invoke Sample", 0);  
    }  
}  
  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" IntPtr MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
void main(void) {  
     String* pText = L"Hello World!";  
     String* pCaption = L"Platform Invoke Sample";  
     MessageBox(0, pText, pCaption, 0);  
}  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [指定字符集](../../../docs/framework/interop/specifying-a-character-set.md)