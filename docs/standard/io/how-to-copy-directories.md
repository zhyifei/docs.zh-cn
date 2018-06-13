---
title: 如何：复制目录
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1cfe07af216da1c35b093a1ca23e4d48c60a7bfe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571230"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="26bab-102">如何：复制目录</span><span class="sxs-lookup"><span data-stu-id="26bab-102">How to: Copy Directories</span></span>
<span data-ttu-id="26bab-103">此示例演示如何使用 I/O 类将目录下的内容同步复制到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="26bab-103">This example demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span> <span data-ttu-id="26bab-104">在此示例中，用户可以指定是否同时复制子目录。</span><span class="sxs-lookup"><span data-stu-id="26bab-104">In this example, the user can specify whether to also copy the subdirectories.</span></span> <span data-ttu-id="26bab-105">如果复制子目录，则此示例中的方法将通过对每个后续子目录调用其自身的方法来递归复制它们，直到再也没有子目录可以复制为止。</span><span class="sxs-lookup"><span data-stu-id="26bab-105">If the subdirectories are copied, the method in this example recursively copies them by calling itself on each subsequent subdirectory until there are no more to copy.</span></span>  
  
 <span data-ttu-id="26bab-106">有关异步复制文件的示例，请参阅 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)。</span><span class="sxs-lookup"><span data-stu-id="26bab-106">For an example of copying files asynchronously, see [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="26bab-107">示例</span><span class="sxs-lookup"><span data-stu-id="26bab-107">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="26bab-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="26bab-108">See Also</span></span>  
 <xref:System.IO.FileInfo>  
 <xref:System.IO.DirectoryInfo>  
 <xref:System.IO.FileStream>  
 [<span data-ttu-id="26bab-109">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="26bab-109">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="26bab-110">通用 I/O 任务</span><span class="sxs-lookup"><span data-stu-id="26bab-110">Common I/O Tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)  
 [<span data-ttu-id="26bab-111">异步文件 I/O</span><span class="sxs-lookup"><span data-stu-id="26bab-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
