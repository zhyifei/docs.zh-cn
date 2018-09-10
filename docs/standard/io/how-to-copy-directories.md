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
ms.openlocfilehash: 6f2c2fbd58b10af80a2a233cbd4211befe2dbd33
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216049"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="4889a-102">如何：复制目录</span><span class="sxs-lookup"><span data-stu-id="4889a-102">How to: Copy Directories</span></span>
<span data-ttu-id="4889a-103">此示例演示如何使用 I/O 类将目录下的内容同步复制到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="4889a-103">This example demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span> <span data-ttu-id="4889a-104">在此示例中，用户可以指定是否同时复制子目录。</span><span class="sxs-lookup"><span data-stu-id="4889a-104">In this example, the user can specify whether to also copy the subdirectories.</span></span> <span data-ttu-id="4889a-105">如果复制子目录，则此示例中的方法将通过对每个后续子目录调用其自身的方法来递归复制它们，直到再也没有子目录可以复制为止。</span><span class="sxs-lookup"><span data-stu-id="4889a-105">If the subdirectories are copied, the method in this example recursively copies them by calling itself on each subsequent subdirectory until there are no more to copy.</span></span>  
  
 <span data-ttu-id="4889a-106">有关异步复制文件的示例，请参阅 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)。</span><span class="sxs-lookup"><span data-stu-id="4889a-106">For an example of copying files asynchronously, see [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4889a-107">示例</span><span class="sxs-lookup"><span data-stu-id="4889a-107">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4889a-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4889a-108">See also</span></span>

- <xref:System.IO.FileInfo>  
- <xref:System.IO.DirectoryInfo>  
- <xref:System.IO.FileStream>  
- [<span data-ttu-id="4889a-109">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="4889a-109">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
- [<span data-ttu-id="4889a-110">通用 I/O 任务</span><span class="sxs-lookup"><span data-stu-id="4889a-110">Common I/O Tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)  
- [<span data-ttu-id="4889a-111">异步文件 I/O</span><span class="sxs-lookup"><span data-stu-id="4889a-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
