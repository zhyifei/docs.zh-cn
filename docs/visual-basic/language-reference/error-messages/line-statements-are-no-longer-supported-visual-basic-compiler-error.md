---
title: '&#39;行&#39;语句将不再支持 （Visual Basic 编译器错误）'
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 06bba0ebfc2faec24f4720c45de3bdcfec993499
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587874"
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="9e574-102">&#39;行&#39;语句将不再支持 （Visual Basic 编译器错误）</span><span class="sxs-lookup"><span data-stu-id="9e574-102">&#39;Line&#39; statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="9e574-103">不再支持行语句。</span><span class="sxs-lookup"><span data-stu-id="9e574-103">Line statements are no longer supported.</span></span> <span data-ttu-id="9e574-104">文件 I/O 功能是可用作`Microsoft.VisualBasic.FileSystem.LineInput`，图形功能可用作`System.Drawing.Graphics.DrawLine`。</span><span class="sxs-lookup"><span data-stu-id="9e574-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="9e574-105">**错误 ID:** BC30830</span><span class="sxs-lookup"><span data-stu-id="9e574-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9e574-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9e574-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="9e574-107">如果执行文件访问，请使用`Microsoft.VisualBasic.FileSystem.LineInput`。</span><span class="sxs-lookup"><span data-stu-id="9e574-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2.  <span data-ttu-id="9e574-108">如果执行图形，请使用`System.Drawing.Graphics.Drawline`。</span><span class="sxs-lookup"><span data-stu-id="9e574-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e574-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e574-109">See Also</span></span>  
 <xref:System.IO>  
 <xref:System.Drawing>  
 [<span data-ttu-id="9e574-110">使用 Visual Basic 访问文件</span><span class="sxs-lookup"><span data-stu-id="9e574-110">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
