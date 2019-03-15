---
title: 由于内部错误，无法获取完整的操作系统名
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 6a0e24743c861ba92fc284a84fa4ef26e2ee48a8
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58022752"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="625bb-102">由于内部错误，无法获取完整的操作系统名</span><span class="sxs-lookup"><span data-stu-id="625bb-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="625bb-103">由于内部错误，无法获取完整的操作系统名。</span><span class="sxs-lookup"><span data-stu-id="625bb-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="625bb-104">这可能由当前计算机上不存在 WMI 导致。</span><span class="sxs-lookup"><span data-stu-id="625bb-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="625bb-105">对 `My.Computer.Info.OSFullName` 属性的调用失败。</span><span class="sxs-lookup"><span data-stu-id="625bb-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="625bb-106">此失败的可能原因是当前计算机上是否未安装 Windows Management Instrumentation (WMI)。</span><span class="sxs-lookup"><span data-stu-id="625bb-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="625bb-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="625bb-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="625bb-108">将调用周围的 `Try...Catch` 块添加到 `My.Computer.Info.OSFullName` 属性。</span><span class="sxs-lookup"><span data-stu-id="625bb-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="625bb-109">有关 WMI 和如何安装它的详细信息，请转到和"Windows Management Instrumentation Core"搜索。</span><span class="sxs-lookup"><span data-stu-id="625bb-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625bb-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="625bb-110">See also</span></span>

- [<span data-ttu-id="625bb-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="625bb-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="625bb-112">在 .NET 中处理和引发异常</span><span class="sxs-lookup"><span data-stu-id="625bb-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="625bb-113">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="625bb-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
