---
title: "由于内部错误，无法获取完整的操作系统名"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65796c41d2a9fbd03517e7b15bc6b566ba4364fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="14f16-102">由于内部错误，无法获取完整的操作系统名</span><span class="sxs-lookup"><span data-stu-id="14f16-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="14f16-103">由于内部错误，无法获取完整的操作系统名。</span><span class="sxs-lookup"><span data-stu-id="14f16-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="14f16-104">这可能由当前计算机上不存在 WMI 导致。</span><span class="sxs-lookup"><span data-stu-id="14f16-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="14f16-105">对 `My.Computer.Info.OSFullName` 属性的调用失败。</span><span class="sxs-lookup"><span data-stu-id="14f16-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="14f16-106">此失败的可能原因是当前计算机上是否未安装 Windows Management Instrumentation (WMI)。</span><span class="sxs-lookup"><span data-stu-id="14f16-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14f16-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="14f16-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="14f16-108">将调用周围的 `Try...Catch` 块添加到 `My.Computer.Info.OSFullName` 属性。</span><span class="sxs-lookup"><span data-stu-id="14f16-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="14f16-109">有关 WMI 和如何安装它的详细信息，请转到和"Windows Management Instrumentation Core"搜索。</span><span class="sxs-lookup"><span data-stu-id="14f16-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f16-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14f16-110">See Also</span></span>  
 [<span data-ttu-id="14f16-111">My.Computer.Info.OSFullName 属性</span><span class="sxs-lookup"><span data-stu-id="14f16-111">My.Computer.Info.OSFullName Property</span></span>](http://msdn.microsoft.com/en-us/b3b0fbd1-4dc5-428a-ad04-0d9fc9c2a9be)  
 [<span data-ttu-id="14f16-112">异常和 Visual Basic 中的错误处理</span><span class="sxs-lookup"><span data-stu-id="14f16-112">Exception and Error Handling in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/3e351e73-cf23-40ab-8b60-05794160529e)  
 [<span data-ttu-id="14f16-113">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="14f16-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
