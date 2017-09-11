---
title: "如何：读取文本文件中的内容（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- StreamReader.ReadToEnd
dev_langs:
- CSharp
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bd0ad3e062c4d4b32fb6140cacba9a4a32674759
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a><span data-ttu-id="9fe06-102">如何：读取文本文件中的内容（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9fe06-102">How to: Read From a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="9fe06-103">此示例通过使用 <xref:System.IO.File?displayProperty=fullName> 类的 <xref:System.IO.File.ReadAllText%2A> 和 <xref:System.IO.File.ReadAllLines%2A> 静态方法来确定文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="9fe06-103">This example reads the contents of a text file by using the static methods <xref:System.IO.File.ReadAllText%2A> and <xref:System.IO.File.ReadAllLines%2A> from the <xref:System.IO.File?displayProperty=fullName> class.</span></span>  
  
 <span data-ttu-id="9fe06-104">有关使用 <xref:System.IO.StreamReader> 的示例，请参阅[如何：一次一行地读取文本文件](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe06-104">For an example that uses <xref:System.IO.StreamReader>, see [How to: Read a Text File One Line at a Time](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fe06-105">此示例所用的文件是在主题[如何：写入文本文件](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)中创建的。</span><span class="sxs-lookup"><span data-stu-id="9fe06-105">The files that are used in this example are created in the topic [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fe06-106">示例</span><span class="sxs-lookup"><span data-stu-id="9fe06-106">Example</span></span>  
 <span data-ttu-id="9fe06-107">[!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fe06-107">[!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9fe06-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="9fe06-108">Compiling the Code</span></span>  
 <span data-ttu-id="9fe06-109">将代码复制并粘贴到 C# 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="9fe06-109">Copy the code and paste it into a C# console application.</span></span>  
  
 <span data-ttu-id="9fe06-110">如果不使用[如何：写入文本文件](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)中的文本文件，请将 `ReadAllText` 和 `ReadAllLines` 的参数替换为计算机上的适当路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="9fe06-110">If you are not using the text files from [How to: Write to a Text File](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), replace the argument to `ReadAllText` and `ReadAllLines` with the appropriate path and file name on your computer.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9fe06-111">可靠编程</span><span class="sxs-lookup"><span data-stu-id="9fe06-111">Robust Programming</span></span>  
 <span data-ttu-id="9fe06-112">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="9fe06-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="9fe06-113">不存在该文件，或者指定位置不存在该文件。</span><span class="sxs-lookup"><span data-stu-id="9fe06-113">The file doesn't exist or doesn't exist at the specified location.</span></span> <span data-ttu-id="9fe06-114">检查文件名的路径和拼写。</span><span class="sxs-lookup"><span data-stu-id="9fe06-114">Check the path and the spelling of the file name.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9fe06-115">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="9fe06-115">.NET Framework Security</span></span>  
 <span data-ttu-id="9fe06-116">不要依赖文件名来确定文件的内容。</span><span class="sxs-lookup"><span data-stu-id="9fe06-116">Do not rely on the name of a file to determine the contents of the file.</span></span> <span data-ttu-id="9fe06-117">例如，文件 `myFile.cs` 可能不是 C# 源文件。</span><span class="sxs-lookup"><span data-stu-id="9fe06-117">For example, the file `myFile.cs` might not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe06-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fe06-118">See Also</span></span>  
 <span data-ttu-id="9fe06-119"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9fe06-119"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="9fe06-120">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fe06-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9fe06-121">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9fe06-121">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

