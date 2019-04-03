---
title: 输入超出文件尾
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 63b099144b9da601a7b52a738f5a3173097ae257
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813153"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="e2de6-102">输入超出文件尾</span><span class="sxs-lookup"><span data-stu-id="e2de6-102">Input past end of file</span></span>
<span data-ttu-id="e2de6-103">任一`Input`语句正在读取的文件为空或其中的所有数据都使用，或者您都使用`EOF`函数和一个文件打开以进行二进制访问。</span><span class="sxs-lookup"><span data-stu-id="e2de6-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e2de6-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e2de6-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="e2de6-105">使用`EOF`函数之前`Input`语句，以检测到文件末尾。</span><span class="sxs-lookup"><span data-stu-id="e2de6-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="e2de6-106">如果为进行二进制访问打开该文件，则使用`Seek`和`Loc`。</span><span class="sxs-lookup"><span data-stu-id="e2de6-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2de6-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2de6-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
