---
title: "如何：写入文本文件（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c576536947cdb4984d6e5ce67c8377fe23b354c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="8b498-102">如何：写入文本文件（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8b498-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="8b498-103">以下示例给出了将文本写入文件的各种方法。</span><span class="sxs-lookup"><span data-stu-id="8b498-103">These examples show various ways to write text to a file.</span></span>  <span data-ttu-id="8b498-104">前两个示例对 <xref:System.IO.File?displayProperty=nameWithType> 类使用静态便捷方法以将任何 IEnumerable\<string> 的每个元素和字符串写入文本文件。</span><span class="sxs-lookup"><span data-stu-id="8b498-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=nameWithType> class to write each element of any IEnumerable\<string> and a string to a text file.</span></span>  <span data-ttu-id="8b498-105">示例 3 展示了在写入文件时必须分别处理文本的每一行时，如何将文本添加到文件。</span><span class="sxs-lookup"><span data-stu-id="8b498-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span>  <span data-ttu-id="8b498-106">示例 1-3 覆盖文件中的所有现有内容，但示例 4 展示如何将文本追加到现有文件。</span><span class="sxs-lookup"><span data-stu-id="8b498-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="8b498-107">这些示例均会将字符串文本写入文件，但是你更有可能需要使用 <xref:System.String.Format%2A> 方法，此方法具有很多用于写入不同类型值的控件，包括在字段中左右对齐、有无边距等。</span><span class="sxs-lookup"><span data-stu-id="8b498-107">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="8b498-108">还可以使用 C# [字符串内插](../../../csharp/language-reference/keywords/interpolated-strings.md)功能。</span><span class="sxs-lookup"><span data-stu-id="8b498-108">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b498-109">示例</span><span class="sxs-lookup"><span data-stu-id="8b498-109">Example</span></span>  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 <span data-ttu-id="8b498-110">这些示例均会将字符串文本写入文件，但是你更有可能需要使用 <xref:System.String.Format%2A> 方法，此方法具有很多用于写入不同类型值的控件，包括在字段中左右对齐、有无边距等。</span><span class="sxs-lookup"><span data-stu-id="8b498-110">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="8b498-111">还可以使用 C# [字符串内插](../../../csharp/language-reference/keywords/interpolated-strings.md)功能。</span><span class="sxs-lookup"><span data-stu-id="8b498-111">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8b498-112">可靠编程</span><span class="sxs-lookup"><span data-stu-id="8b498-112">Robust Programming</span></span>  
 <span data-ttu-id="8b498-113">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="8b498-113">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8b498-114">文件已存在并且为只读。</span><span class="sxs-lookup"><span data-stu-id="8b498-114">The file exists and is read-only.</span></span>  
  
-   <span data-ttu-id="8b498-115">路径名可能太长。</span><span class="sxs-lookup"><span data-stu-id="8b498-115">The path name may be too long.</span></span>  
  
-   <span data-ttu-id="8b498-116">磁盘可能已满。</span><span class="sxs-lookup"><span data-stu-id="8b498-116">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b498-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b498-117">See Also</span></span>  
 [<span data-ttu-id="8b498-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8b498-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8b498-119">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8b498-119">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)  
 [<span data-ttu-id="8b498-120">示例：将集合保存到应用程序存储</span><span class="sxs-lookup"><span data-stu-id="8b498-120">Sample: Save a collection to Application Storage</span></span>](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
