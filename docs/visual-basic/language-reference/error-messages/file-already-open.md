---
title: 文件已打开
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3305831e840510e3f0b5bcb8bf847e39ea3ee4ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="file-already-open"></a><span data-ttu-id="ea836-102">文件已打开</span><span class="sxs-lookup"><span data-stu-id="ea836-102">File already open</span></span>
<span data-ttu-id="ea836-103">有时必须在另一部分之前关闭的文件`FileOpen`或位置执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="ea836-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="ea836-104">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="ea836-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="ea836-105">顺序输出模式`FileOpen`已打开的文件执行操作</span><span class="sxs-lookup"><span data-stu-id="ea836-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="ea836-106">某个语句引用打开的文件。</span><span class="sxs-lookup"><span data-stu-id="ea836-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea836-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ea836-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="ea836-108">执行语句之前关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="ea836-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea836-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea836-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
