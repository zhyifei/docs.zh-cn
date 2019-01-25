---
title: 由于内部错误，无法获取完整的操作系统名
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: df7a91ea5763c0fe4b7a1993bec29f1b1bb43fcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723289"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="cceb0-102">由于内部错误，无法获取完整的操作系统名</span><span class="sxs-lookup"><span data-stu-id="cceb0-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="cceb0-103">由于内部错误，无法获取完整的操作系统名。</span><span class="sxs-lookup"><span data-stu-id="cceb0-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="cceb0-104">这可能由当前计算机上不存在 WMI 导致。</span><span class="sxs-lookup"><span data-stu-id="cceb0-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="cceb0-105">对 `My.Computer.Info.OSFullName` 属性的调用失败。</span><span class="sxs-lookup"><span data-stu-id="cceb0-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="cceb0-106">此失败的可能原因是当前计算机上是否未安装 Windows Management Instrumentation (WMI)。</span><span class="sxs-lookup"><span data-stu-id="cceb0-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cceb0-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="cceb0-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="cceb0-108">将调用周围的 `Try...Catch` 块添加到 `My.Computer.Info.OSFullName` 属性。</span><span class="sxs-lookup"><span data-stu-id="cceb0-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="cceb0-109">有关 WMI 和如何安装它的详细信息，请转到和"Windows Management Instrumentation Core"搜索。</span><span class="sxs-lookup"><span data-stu-id="cceb0-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cceb0-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="cceb0-110">See also</span></span>
- [<span data-ttu-id="cceb0-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="cceb0-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="cceb0-112">Visual Basic 中的异常与错误处理</span><span class="sxs-lookup"><span data-stu-id="cceb0-112">Exception and Error Handling in Visual Basic</span></span>](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)
- [<span data-ttu-id="cceb0-113">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="cceb0-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
