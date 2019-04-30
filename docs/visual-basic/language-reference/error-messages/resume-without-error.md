---
title: 无错误继续执行
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 61332486b20af66af24eac06b222a38353578c16
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055155"
---
# <a name="resume-without-error"></a><span data-ttu-id="4b3d2-102">无错误继续执行</span><span class="sxs-lookup"><span data-stu-id="4b3d2-102">Resume without error</span></span>
<span data-ttu-id="4b3d2-103">一个`Resume`语句出现在错误处理代码之外或代码改为使用错误处理程序，即使没有错误。</span><span class="sxs-lookup"><span data-stu-id="4b3d2-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b3d2-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4b3d2-104">To correct this error</span></span>  
  
1. <span data-ttu-id="4b3d2-105">移动`Resume`语句到错误处理程序，或将其删除。</span><span class="sxs-lookup"><span data-stu-id="4b3d2-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="4b3d2-106">跳转到标签不能过程中出现，因此，请搜索的标签用于标识错误处理程序的过程。</span><span class="sxs-lookup"><span data-stu-id="4b3d2-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="4b3d2-107">如果找到指定的目标为重复的标签`GoTo`语句而非`On Error GoTo`语句中，更改行标签，以便与其预期目标。</span><span class="sxs-lookup"><span data-stu-id="4b3d2-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3d2-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b3d2-108">See also</span></span>

- [<span data-ttu-id="4b3d2-109">Resume 语句</span><span class="sxs-lookup"><span data-stu-id="4b3d2-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="4b3d2-110">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="4b3d2-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
