---
title: 指定字符集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 798fcacab5bd74dbd6569a68a3b598c0bb63a0a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087737"
---
# <a name="specifying-a-character-set"></a>指定字符集
<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段控制字符串封送，并确定平台调用在 DLL 中查找函数名的方式。 本主题将介绍这两种行为。  
  
 某些 API 导出采用字符串自变量的函数的两个版本：窄版 (ANSI) 和宽版 (Unicode)。 例如，Windows API 包含 MessageBox 函数的以下入口点名称：  
  
-   **MessageBoxA**  
  
     提供 ANSI 格式的 1 字节字符，由附加到入口点名称后的“A”区分。 调用 MessageBoxA 始终以 ANSI 格式封送字符串。  
  
-   **MessageBoxW**  
  
     提供 Unicode 格式的 2 字节字符，由附加到入口点名称后的“W”区分。 调用 MessageBoxW 始终以 Unicode 格式封送字符串。  
  
## <a name="string-marshaling-and-name-matching"></a>字符串封送和名称匹配  
 `CharSet` 字段接受以下值：  
  
 <xref:System.Runtime.InteropServices.CharSet.Ansi>（默认值）  
  
-   字符串封送  
  
     平台调用将字符串从托管格式 (Unicode) 封送为 ANSI 格式。  
  
-   名称匹配  
  
     如果 <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> 字段为 `true`（[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 中默认为此值），平台调用仅搜索你指定的名称。 例如，如果指定“MessageBox”，则平台调用搜索“MessageBox”，如果无法找到精确拼写，则将失败。  
  
     如果 `ExactSpelling` 字段为 `false`（C++ 和 C# 中默认为此值），平台调用先搜索未损坏的别名 (MessageBox)，如果找不到未损坏的别名，再搜索损坏的名称 (MessageBoxA)。 请注意，ANSI 名称匹配行为与 Unicode 名称匹配行为不同。  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
-   字符串封送  
  
     平台调用将字符串从托管格式 (Unicode) 复制为 Unicode 格式。  
  
-   名称匹配  
  
     如果 `ExactSpelling` 字段为 `true`（[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 中默认为此值），平台调用仅搜索你指定的名称。 例如，如果指定“MessageBox” ，则平台调用搜索“MessageBox”，如果无法找到精确拼写，则将失败。  
  
     如果 `ExactSpelling` 字段为 `false`（C++ 和 C# 中默认为此值），平台调用先搜索损坏的名称 (MessageBoxW)，如果找不到损坏的名称，再搜索未损坏的别名 (MessageBox)。 请注意，Unicode 名称匹配行为与 ANSI 名称匹配行为不同。  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
-   平台调用在运行时根据目标平台在 ANSI 和 Unicode 格式之间进行选择。  
  
## <a name="specifying-a-character-set-in-visual-basic"></a>在 Visual Basic 中指定字符集  
 以下示例声明“MessageBox”函数三次，每次使用不同的字符集行为。 通过将“Ansi”、“Unicode”或“Auto”关键字添加到声明语句中，就可以在 Visual Basic 中指定字符集行为。  
  
 如果省略字符集关键字，正如在第一个声明语句中那样，则 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段默认为 ANSI 字符集。 示例中的第二个和第三个语句使用关键字显式指定字符集。  
  
```vb
Imports System

Friend Class WindowsAPI
    Friend Shared Declare Function MessageBoxA Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Shared Declare Unicode Function MessageBoxW Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Shared Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="specifying-a-character-set-in-c-and-c"></a>在 C# 和 C++ 中指定字符集  
 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段将基础字符集标识为 ANSI 或 Unicode。 字符集控制应如何封送方法的字符串自变量。 使用以下形式之一来指示字符集：  
  
```csharp
[DllImport("DllName", CharSet = CharSet.Ansi)]
[DllImport("DllName", CharSet = CharSet.Unicode)]
[DllImport("DllName", CharSet = CharSet.Auto)]
```
  
```cpp
[DllImport("DllName", CharSet = CharSet::Ansi)]
[DllImport("DllName", CharSet = CharSet::Unicode)]
[DllImport("DllName", CharSet = CharSet::Auto)]
```
  
 以下示例显示“MessageBox”函数的三个托管定义，它们是指定字符集的结果。 在第一个定义中，通过省略，`CharSet` 字段默认为 ANSI 字符集。  
  
```csharp  
using System;
using System.Runtime.InteropServices;

internal static class WindowsAPI
{
    [DllImport("user32.dll")]
    internal static extern int MessageBoxA(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Unicode)]
    internal static extern int MessageBoxW(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Auto)]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```  
  
```cpp
typedef void* HWND;

// Can use MessageBox or MessageBoxA.
[DllImport("user32")]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Can use MessageBox or MessageBoxW.
[DllImport("user32", CharSet = CharSet::Unicode)]
extern "C" int MessageBoxW(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Must use MessageBox.
[DllImport("user32", CharSet = CharSet::Auto)]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a>请参阅

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [平台调用示例](../../../docs/framework/interop/platform-invoke-examples.md)
- [用平台调用封送数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
