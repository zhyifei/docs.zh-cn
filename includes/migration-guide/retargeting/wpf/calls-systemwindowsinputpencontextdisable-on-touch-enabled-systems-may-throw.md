---
ms.openlocfilehash: 0778285ef1b5702bd79743038a1bd21ba04612d6
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760973"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="05333-101">在启用触摸的系统上调用 System.Windows.Input.PenContext.Disable 可能会引发 ArgumentException</span><span class="sxs-lookup"><span data-stu-id="05333-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="05333-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="05333-102">Details</span></span>|<span data-ttu-id="05333-103">在某些情况下，在启用触摸的系统上调用内部 <strong>System.Windows.Intput.PenContext.Disable</strong> 方法可能会因为重新进入而引发未处理的 <code>T:System.ArgumentException</code>。</span><span class="sxs-lookup"><span data-stu-id="05333-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="05333-104">建议</span><span class="sxs-lookup"><span data-stu-id="05333-104">Suggestion</span></span>|<span data-ttu-id="05333-105">此问题已在 .NET Framework 4.7 中得到解决。</span><span class="sxs-lookup"><span data-stu-id="05333-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="05333-106">若要避免此异常，升级到 .NET Framework 4.7 及以上版本。</span><span class="sxs-lookup"><span data-stu-id="05333-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="05333-107">范围</span><span class="sxs-lookup"><span data-stu-id="05333-107">Scope</span></span>|<span data-ttu-id="05333-108">边缘</span><span class="sxs-lookup"><span data-stu-id="05333-108">Edge</span></span>|
|<span data-ttu-id="05333-109">版本</span><span class="sxs-lookup"><span data-stu-id="05333-109">Version</span></span>|<span data-ttu-id="05333-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="05333-110">4.6.1</span></span>|
|<span data-ttu-id="05333-111">类型</span><span class="sxs-lookup"><span data-stu-id="05333-111">Type</span></span>|<span data-ttu-id="05333-112">重定目标</span><span class="sxs-lookup"><span data-stu-id="05333-112">Retargeting</span></span>|

