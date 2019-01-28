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
ms.openlocfilehash: 45810390ced8584ea7b37908a9e4af8d3da73f34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549845"
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="ed376-102">指定字符集</span><span class="sxs-lookup"><span data-stu-id="ed376-102">Specifying a Character Set</span></span>
<span data-ttu-id="ed376-103"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段控制字符串封送，并确定平台调用在 DLL 中查找函数名的方式。</span><span class="sxs-lookup"><span data-stu-id="ed376-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="ed376-104">本主题将介绍这两种行为。</span><span class="sxs-lookup"><span data-stu-id="ed376-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="ed376-105">某些 API 导出采用字符串自变量的函数的两个版本：窄版 (ANSI) 和宽版 (Unicode)。</span><span class="sxs-lookup"><span data-stu-id="ed376-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="ed376-106">例如，Win32 API 包含“MessageBox”函数的以下入口点名称：</span><span class="sxs-lookup"><span data-stu-id="ed376-106">The Win32 API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
-   <span data-ttu-id="ed376-107">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="ed376-107">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="ed376-108">提供 ANSI 格式的 1 字节字符，由附加到入口点名称后的“A”区分。</span><span class="sxs-lookup"><span data-stu-id="ed376-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="ed376-109">对“MessageBoxA”的调用始终采用 ANSI 格式封送字符串，这在 Windows 95 和 Windows 98 平台上很常见。</span><span class="sxs-lookup"><span data-stu-id="ed376-109">Calls to **MessageBoxA** always marshal strings in ANSI format, as is common on Windows 95 and Windows 98 platforms.</span></span>  
  
-   <span data-ttu-id="ed376-110">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="ed376-110">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="ed376-111">提供 Unicode 格式的 2 字节字符，由附加到入口点名称后的“W”区分。</span><span class="sxs-lookup"><span data-stu-id="ed376-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="ed376-112">对“MessageBoxW”的调用始终采用 Unicode 格式封送字符串，这在 Windows NT、Windows 2000 和 Windows XP 平台上很常见。</span><span class="sxs-lookup"><span data-stu-id="ed376-112">Calls to **MessageBoxW** always marshal strings in Unicode format, as is common on Windows NT, Windows 2000, and Windows XP platforms.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="ed376-113">字符串封送和名称匹配</span><span class="sxs-lookup"><span data-stu-id="ed376-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="ed376-114">“CharSet”字段接受以下值：</span><span class="sxs-lookup"><span data-stu-id="ed376-114">The **CharSet** field accepts the following values:</span></span>  
  
 <span data-ttu-id="ed376-115">**CharSet.Ansi**（默认值）</span><span class="sxs-lookup"><span data-stu-id="ed376-115">**CharSet.Ansi** (default value)</span></span>  
  
-   <span data-ttu-id="ed376-116">字符串封送</span><span class="sxs-lookup"><span data-stu-id="ed376-116">String marshaling</span></span>  
  
     <span data-ttu-id="ed376-117">平台调用将字符串从托管格式 (Unicode) 封送为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="ed376-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
-   <span data-ttu-id="ed376-118">名称匹配</span><span class="sxs-lookup"><span data-stu-id="ed376-118">Name matching</span></span>  
  
     <span data-ttu-id="ed376-119">当 <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> 字段为“true”时（[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 中默认为此值），平台调用仅搜索你指定的名称。</span><span class="sxs-lookup"><span data-stu-id="ed376-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="ed376-120">例如，如果指定“MessageBox”，则平台调用搜索“MessageBox”，如果无法找到精确拼写，则将失败。</span><span class="sxs-lookup"><span data-stu-id="ed376-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="ed376-121">“ExactSpelling”字段为“false”时（C++ 和 C# 中默认为此值），平台调用首先搜索未损坏的别名（MessageBox），如果未找到未损坏的别名，再搜索损坏的名称（MessageBoxA）。</span><span class="sxs-lookup"><span data-stu-id="ed376-121">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="ed376-122">请注意，ANSI 名称匹配行为与 Unicode 名称匹配行为不同。</span><span class="sxs-lookup"><span data-stu-id="ed376-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <span data-ttu-id="ed376-123">**CharSet.Unicode**</span><span class="sxs-lookup"><span data-stu-id="ed376-123">**CharSet.Unicode**</span></span>  
  
-   <span data-ttu-id="ed376-124">字符串封送</span><span class="sxs-lookup"><span data-stu-id="ed376-124">String marshaling</span></span>  
  
     <span data-ttu-id="ed376-125">平台调用将字符串从托管格式 (Unicode) 复制为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="ed376-125">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
-   <span data-ttu-id="ed376-126">名称匹配</span><span class="sxs-lookup"><span data-stu-id="ed376-126">Name matching</span></span>  
  
     <span data-ttu-id="ed376-127">当“ExactSpelling”字段为“true”时（[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 中默认为此值），平台调用仅搜索你指定的名称。</span><span class="sxs-lookup"><span data-stu-id="ed376-127">When the **ExactSpelling** field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="ed376-128">例如，如果指定“MessageBox” ，则平台调用搜索“MessageBox”，如果无法找到精确拼写，则将失败。</span><span class="sxs-lookup"><span data-stu-id="ed376-128">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="ed376-129">当“ExactSpelling”字段为“false”时（C++ 和 C# 中默认为此值），平台调用首先搜索已损坏的名称（MessageBoxW），如果未找到已损坏的名称，再搜索未损坏的别名（MessageBox）。</span><span class="sxs-lookup"><span data-stu-id="ed376-129">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="ed376-130">请注意，Unicode 名称匹配行为与 ANSI 名称匹配行为不同。</span><span class="sxs-lookup"><span data-stu-id="ed376-130">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <span data-ttu-id="ed376-131">**CharSet.Auto**</span><span class="sxs-lookup"><span data-stu-id="ed376-131">**CharSet.Auto**</span></span>  
  
-   <span data-ttu-id="ed376-132">平台调用在运行时根据目标平台在 ANSI 和 Unicode 格式之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="ed376-132">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="ed376-133">在 Visual Basic 中指定字符集</span><span class="sxs-lookup"><span data-stu-id="ed376-133">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="ed376-134">以下示例声明“MessageBox”函数三次，每次使用不同的字符集行为。</span><span class="sxs-lookup"><span data-stu-id="ed376-134">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="ed376-135">通过将“Ansi”、“Unicode”或“Auto”关键字添加到声明语句中，就可以在 Visual Basic 中指定字符集行为。</span><span class="sxs-lookup"><span data-stu-id="ed376-135">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="ed376-136">如果省略字符集关键字，正如在第一个声明语句中那样，则 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段默认为 ANSI 字符集。</span><span class="sxs-lookup"><span data-stu-id="ed376-136">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="ed376-137">示例中的第二个和第三个语句使用关键字显式指定字符集。</span><span class="sxs-lookup"><span data-stu-id="ed376-137">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
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
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="ed376-138">在 C# 和 C++ 中指定字符集</span><span class="sxs-lookup"><span data-stu-id="ed376-138">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="ed376-139"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段将基础字符集标识为 ANSI 或 Unicode。</span><span class="sxs-lookup"><span data-stu-id="ed376-139">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="ed376-140">字符集控制应如何封送方法的字符串自变量。</span><span class="sxs-lookup"><span data-stu-id="ed376-140">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="ed376-141">使用以下形式之一来指示字符集：</span><span class="sxs-lookup"><span data-stu-id="ed376-141">Use one of the following forms to indicate the character set:</span></span>  
  
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
  
 <span data-ttu-id="ed376-142">以下示例显示“MessageBox”函数的三个托管定义，它们是指定字符集的结果。</span><span class="sxs-lookup"><span data-stu-id="ed376-142">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="ed376-143">在第一个定义中，通过省略，“CharSet”字段默认为 ANSI 字符集。</span><span class="sxs-lookup"><span data-stu-id="ed376-143">In the first definition, by its omission, the **CharSet** field defaults to the ANSI character set.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ed376-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed376-144">See also</span></span>
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="ed376-145">在托管代码中创建原型</span><span class="sxs-lookup"><span data-stu-id="ed376-145">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="ed376-146">平台调用示例</span><span class="sxs-lookup"><span data-stu-id="ed376-146">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="ed376-147">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="ed376-147">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
