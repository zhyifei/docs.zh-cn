---
title: 不再支持“Line”语句（Visual Basic 编译器错误）
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 17025e9a3c87d84a10ddaa7aeef616d985143879
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283200"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="ac43f-102">不再支持“Line”语句（Visual Basic 编译器错误）</span><span class="sxs-lookup"><span data-stu-id="ac43f-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="ac43f-103">不再支持行语句。</span><span class="sxs-lookup"><span data-stu-id="ac43f-103">Line statements are no longer supported.</span></span> <span data-ttu-id="ac43f-104">文件 I/O 功能是可用作`Microsoft.VisualBasic.FileSystem.LineInput`图形功能，可作为`System.Drawing.Graphics.DrawLine`。</span><span class="sxs-lookup"><span data-stu-id="ac43f-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="ac43f-105">**错误 ID:** BC30830</span><span class="sxs-lookup"><span data-stu-id="ac43f-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ac43f-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ac43f-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="ac43f-107">如果执行文件访问，请使用`Microsoft.VisualBasic.FileSystem.LineInput`。</span><span class="sxs-lookup"><span data-stu-id="ac43f-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2.  <span data-ttu-id="ac43f-108">如果执行图形，则请使用 `System.Drawing.Graphics.Drawline`。</span><span class="sxs-lookup"><span data-stu-id="ac43f-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac43f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac43f-109">See also</span></span>
- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="ac43f-110">使用 Visual Basic 访问文件</span><span class="sxs-lookup"><span data-stu-id="ac43f-110">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
