---
title: 文件已打开
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 75a08b411a4afd7ea8e11953f1d465b082faa712
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586665"
---
# <a name="file-already-open"></a><span data-ttu-id="76052-102">文件已打开</span><span class="sxs-lookup"><span data-stu-id="76052-102">File already open</span></span>
<span data-ttu-id="76052-103">有时必须在另一部分之前关闭的文件`FileOpen`或位置执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="76052-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="76052-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="76052-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="76052-105">顺序输出模式`FileOpen`已打开的文件执行操作</span><span class="sxs-lookup"><span data-stu-id="76052-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="76052-106">某个语句引用打开的文件。</span><span class="sxs-lookup"><span data-stu-id="76052-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="76052-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="76052-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="76052-108">执行语句之前关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="76052-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76052-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="76052-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
