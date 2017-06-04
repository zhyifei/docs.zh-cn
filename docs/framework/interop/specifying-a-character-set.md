---
title: "指定字符集 | Microsoft Docs"
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
  - "平台调用中的特性字段, CharSet"
  - "CharSet 字段"
  - "平台调用, 特性字段"
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 指定字符集
<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> 字段控制字符串封送处理并确定平台调用在 DLL 中查找函数名的方式。  本主题将介绍这两种行为。  
  
 对于采用字符串参数的函数，有些 API 将导出它们的两个版本：窄版本 \(ANSI\) 和宽版本 \(Unicode\)。  例如，Win32 API 包含 **MessageBox** 函数的以下入口点名称：  
  
-   **MessageBoxA**  
  
     提供单字节字符 ANSI 格式，其特征是在入口点名称后附加一个“A”。  对 **MessageBoxA** 的调用始终会以 ANSI 格式封送字符串，它常见于 Windows 95 和 Windows 98 平台。  
  
-   **MessageBoxW**  
  
     提供双字节字符 Unicode 格式，其特征是在入口点名称后附加一个“W”。  对 **MessageBoxW** 的调用始终会以 Unicode 格式封送字符串，它常见于 Windows NT、Windows 2000 和 Windows XP 平台。  
  
## 字符串封送处理和名称匹配  
 **CharSet** 字段接受以下值：  
  
 **CharSet.Ansi**（默认值）  
  
-   字符串封送处理  
  
     平台调用将字符串从托管格式 \(Unicode\) 封送为 ANSI 格式。  
  
-   名称匹配  
  
     在 <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=fullName> 字段为 **true**（它是 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 中的默认值）时，平台调用将只搜索您指定的名称。  例如，如果指定 **MessageBox**，则平台调用将搜索 **MessageBox**，如果它找不到完全相同的拼写则失败。  
  
     当 **ExactSpelling** 字段为 **false**（它是 C\+\+ 和 C\# 中的默认值）时，平台调用将首先搜索未处理的别名 \(**MessageBox**\)，如果找不到未处理的别名，则将搜索已处理的名称 \(**MessageBoxA**\)。  请注意，ANSI 名称匹配行为与 Unicode 名称匹配行为不同。  
  
 **CharSet.Unicode**  
  
-   字符串封送处理  
  
     平台调用会将字符串从托管格式 \(Unicode\) 复制为 Unicode 格式。  
  
-   名称匹配  
  
     当 **ExactSpelling** 字段为 **true**（它是 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 中的默认值）时，平台调用将只搜索您指定的名称。  例如，如果指定 **MessageBox**，则平台调用将搜索 **MessageBox**，如果它找不到完全相同的拼写则失败。  
  
     当 **ExactSpelling** 字段为 **false**（它是 C\+\+ 和 C\# 中的默认值）时，平台调用将首先搜索已处理的名称 \(**MessageBoxW**\)，如果找不到已处理的名称，则将搜索未处理的别名 \(**MessageBox**\)。  请注意，Unicode 名称匹配行为与 ANSI 名称匹配行为不同。  
  
 **CharSet.Auto**  
  
-   平台调用在运行时根据目标平台在 ANSI 和 Unicode 格式之间进行选择。  
  
## 在 Visual Basic 中指定字符集  
 下面的示例三次声明 **MessageBox** 函数，每次都具有不同的字符集行为。  可以在 Visual Basic 中指定字符集行为，方法是向声明语句中添加 **Ansi**、**Unicode** 或 **Auto** 关键字。  
  
 如果省略字符集关键字（第一个声明语句中就是这样做的），则 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> 字段默认为 ANSI 字符集。  该示例中的第二个语句和第三个语句则使用关键字显式指定字符集。  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## 在 C\# 和 C\+\+ 中指定字符集  
 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> 字段可将基础字符集标识为 ANSI 或 Unicode。  基础字符集用于控制应如何封送方法的字符串参数。  使用以下形式之一可指定字符集：  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 下面的示例演示进行特性化，以指定字符集的 **MessageBox** 函数的三个托管定义。  在第一个定义中，通过省略，使 **CharSet** 字段默认为 ANSI 字符集。  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [平台调用示例](../../../docs/framework/interop/platform-invoke-examples.md)   
 [用平台调用封送数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)