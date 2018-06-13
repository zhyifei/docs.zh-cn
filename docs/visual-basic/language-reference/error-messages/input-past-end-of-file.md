---
title: 输入超出文件尾
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: abd5f5c6e5df262d1deadd74f0a146a8d436ceb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586736"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="07de8-102">输入超出文件尾</span><span class="sxs-lookup"><span data-stu-id="07de8-102">Input past end of file</span></span>
<span data-ttu-id="07de8-103">任一`Input`语句正在读取或为空的文件中，一个在其中使用的所有数据时，或者你都使用`EOF`以二进制访问方式打开文件的函数。</span><span class="sxs-lookup"><span data-stu-id="07de8-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="07de8-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="07de8-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="07de8-105">使用`EOF`函数前立即`Input`检测文件末尾的语句。</span><span class="sxs-lookup"><span data-stu-id="07de8-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="07de8-106">如果该文件打开进行二进制访问时，使用`Seek`和`Loc`。</span><span class="sxs-lookup"><span data-stu-id="07de8-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07de8-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="07de8-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
