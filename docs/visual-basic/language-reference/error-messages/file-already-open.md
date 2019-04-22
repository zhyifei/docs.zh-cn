---
title: 文件已打开
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770329"
---
# <a name="file-already-open"></a><span data-ttu-id="f6ea9-102">文件已打开</span><span class="sxs-lookup"><span data-stu-id="f6ea9-102">File already open</span></span>
<span data-ttu-id="f6ea9-103">有时必须在另一部分之前关闭的文件`FileOpen`或位置执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="f6ea9-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="f6ea9-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="f6ea9-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="f6ea9-105">顺序输出模式`FileOpen`已打开的文件执行操作</span><span class="sxs-lookup"><span data-stu-id="f6ea9-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="f6ea9-106">语句引用打开的文件。</span><span class="sxs-lookup"><span data-stu-id="f6ea9-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f6ea9-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f6ea9-107">To correct this error</span></span>  
  
1. <span data-ttu-id="f6ea9-108">执行该语句之前关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="f6ea9-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ea9-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6ea9-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
