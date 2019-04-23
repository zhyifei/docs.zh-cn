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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087737"
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="baefe-102">指定字符集</span><span class="sxs-lookup"><span data-stu-id="baefe-102">Specifying a Character Set</span></span>
<span data-ttu-id="baefe-103"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段控制字符串封送，并确定平台调用在 DLL 中查找函数名的方式。</span><span class="sxs-lookup"><span data-stu-id="baefe-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="baefe-104">本主题将介绍这两种行为。</span><span class="sxs-lookup"><span data-stu-id="baefe-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="baefe-105">某些 API 导出采用字符串自变量的函数的两个版本：窄版 (ANSI) 和宽版 (Unicode)。</span><span class="sxs-lookup"><span data-stu-id="baefe-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="baefe-106">例如，Windows API 包含 MessageBox 函数的以下入口点名称：</span><span class="sxs-lookup"><span data-stu-id="baefe-106">The Windows API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
-   **<span data-ttu-id="baefe-107">MessageBoxA</span><span class="sxs-lookup"><span data-stu-id="baefe-107">MessageBoxA</span></span>**  
  
     <span data-ttu-id="baefe-108">提供 ANSI 格式的 1 字节字符，由附加到入口点名称后的“A”区分。</span><span class="sxs-lookup"><span data-stu-id="baefe-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="baefe-109">调用 MessageBoxA 始终以 ANSI 格式封送字符串。</span><span class="sxs-lookup"><span data-stu-id="baefe-109">Calls to **MessageBoxA** always marshal strings in ANSI format.</span></span>  
  
-   **<span data-ttu-id="baefe-110">MessageBoxW</span><span class="sxs-lookup"><span data-stu-id="baefe-110">MessageBoxW</span></span>**  
  
     <span data-ttu-id="baefe-111">提供 Unicode 格式的 2 字节字符，由附加到入口点名称后的“W”区分。</span><span class="sxs-lookup"><span data-stu-id="baefe-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="baefe-112">调用 MessageBoxW 始终以 Unicode 格式封送字符串。</span><span class="sxs-lookup"><span data-stu-id="baefe-112">Calls to **MessageBoxW** always marshal strings in Unicode format.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="baefe-113">字符串封送和名称匹配</span><span class="sxs-lookup"><span data-stu-id="baefe-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="baefe-114">`CharSet` 字段接受以下值：</span><span class="sxs-lookup"><span data-stu-id="baefe-114">The `CharSet` field accepts the following values:</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Ansi> <span data-ttu-id="baefe-115">（默认值）</span><span class="sxs-lookup"><span data-stu-id="baefe-115">(default value)</span></span>  
  
-   <span data-ttu-id="baefe-116">字符串封送</span><span class="sxs-lookup"><span data-stu-id="baefe-116">String marshaling</span></span>  
  
     <span data-ttu-id="baefe-117">平台调用将字符串从托管格式 (Unicode) 封送为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="baefe-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
-   <span data-ttu-id="baefe-118">名称匹配</span><span class="sxs-lookup"><span data-stu-id="baefe-118">Name matching</span></span>  
  
     <span data-ttu-id="baefe-119">如果 <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> 字段为 `true`（[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 中默认为此值），平台调用仅搜索你指定的名称。</span><span class="sxs-lookup"><span data-stu-id="baefe-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is `true`, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="baefe-120">例如，如果指定“MessageBox”，则平台调用搜索“MessageBox”，如果无法找到精确拼写，则将失败。</span><span class="sxs-lookup"><span data-stu-id="baefe-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="baefe-121">如果 `ExactSpelling` 字段为 `false`（C++ 和 C# 中默认为此值），平台调用先搜索未损坏的别名 (MessageBox)，如果找不到未损坏的别名，再搜索损坏的名称 (MessageBoxA)。</span><span class="sxs-lookup"><span data-stu-id="baefe-121">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="baefe-122">请注意，ANSI 名称匹配行为与 Unicode 名称匹配行为不同。</span><span class="sxs-lookup"><span data-stu-id="baefe-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
-   <span data-ttu-id="baefe-123">字符串封送</span><span class="sxs-lookup"><span data-stu-id="baefe-123">String marshaling</span></span>  
  
     <span data-ttu-id="baefe-124">平台调用将字符串从托管格式 (Unicode) 复制为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="baefe-124">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
-   <span data-ttu-id="baefe-125">名称匹配</span><span class="sxs-lookup"><span data-stu-id="baefe-125">Name matching</span></span>  
  
     <span data-ttu-id="baefe-126">如果 `ExactSpelling` 字段为 `true`（[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 中默认为此值），平台调用仅搜索你指定的名称。</span><span class="sxs-lookup"><span data-stu-id="baefe-126">When the `ExactSpelling` field is `true`, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="baefe-127">例如，如果指定“MessageBox” ，则平台调用搜索“MessageBox”，如果无法找到精确拼写，则将失败。</span><span class="sxs-lookup"><span data-stu-id="baefe-127">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="baefe-128">如果 `ExactSpelling` 字段为 `false`（C++ 和 C# 中默认为此值），平台调用先搜索损坏的名称 (MessageBoxW)，如果找不到损坏的名称，再搜索未损坏的别名 (MessageBox)。</span><span class="sxs-lookup"><span data-stu-id="baefe-128">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="baefe-129">请注意，Unicode 名称匹配行为与 ANSI 名称匹配行为不同。</span><span class="sxs-lookup"><span data-stu-id="baefe-129">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
-   <span data-ttu-id="baefe-130">平台调用在运行时根据目标平台在 ANSI 和 Unicode 格式之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="baefe-130">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="baefe-131">在 Visual Basic 中指定字符集</span><span class="sxs-lookup"><span data-stu-id="baefe-131">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="baefe-132">以下示例声明“MessageBox”函数三次，每次使用不同的字符集行为。</span><span class="sxs-lookup"><span data-stu-id="baefe-132">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="baefe-133">通过将“Ansi”、“Unicode”或“Auto”关键字添加到声明语句中，就可以在 Visual Basic 中指定字符集行为。</span><span class="sxs-lookup"><span data-stu-id="baefe-133">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="baefe-134">如果省略字符集关键字，正如在第一个声明语句中那样，则 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段默认为 ANSI 字符集。</span><span class="sxs-lookup"><span data-stu-id="baefe-134">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="baefe-135">示例中的第二个和第三个语句使用关键字显式指定字符集。</span><span class="sxs-lookup"><span data-stu-id="baefe-135">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
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
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="baefe-136">在 C# 和 C++ 中指定字符集</span><span class="sxs-lookup"><span data-stu-id="baefe-136">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="baefe-137"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段将基础字符集标识为 ANSI 或 Unicode。</span><span class="sxs-lookup"><span data-stu-id="baefe-137">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="baefe-138">字符集控制应如何封送方法的字符串自变量。</span><span class="sxs-lookup"><span data-stu-id="baefe-138">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="baefe-139">使用以下形式之一来指示字符集：</span><span class="sxs-lookup"><span data-stu-id="baefe-139">Use one of the following forms to indicate the character set:</span></span>  
  
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
  
 <span data-ttu-id="baefe-140">以下示例显示“MessageBox”函数的三个托管定义，它们是指定字符集的结果。</span><span class="sxs-lookup"><span data-stu-id="baefe-140">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="baefe-141">在第一个定义中，通过省略，`CharSet` 字段默认为 ANSI 字符集。</span><span class="sxs-lookup"><span data-stu-id="baefe-141">In the first definition, by its omission, the `CharSet` field defaults to the ANSI character set.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="baefe-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="baefe-142">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="baefe-143">在托管代码中创建原型</span><span class="sxs-lookup"><span data-stu-id="baefe-143">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="baefe-144">平台调用示例</span><span class="sxs-lookup"><span data-stu-id="baefe-144">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="baefe-145">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="baefe-145">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
