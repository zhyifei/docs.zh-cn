---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887734"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="e62a1-101">在启用触摸的系统上调用 System.Windows.Input.PenContext.Disable 可能会引发 ArgumentException</span><span class="sxs-lookup"><span data-stu-id="e62a1-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e62a1-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="e62a1-102">Details</span></span>|<span data-ttu-id="e62a1-103">在某些情况下，在启用触摸的系统上调用内部 **System.Windows.Intput.PenContext.Disable** 方法可能会因为重新进入而引发未处理的 <code>T:System.ArgumentException</code>。</span><span class="sxs-lookup"><span data-stu-id="e62a1-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="e62a1-104">建议</span><span class="sxs-lookup"><span data-stu-id="e62a1-104">Suggestion</span></span>|<span data-ttu-id="e62a1-105">此问题已在 .NET Framework 4.7 中得到解决。</span><span class="sxs-lookup"><span data-stu-id="e62a1-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="e62a1-106">若要避免此异常，升级到 .NET Framework 4.7 及以上版本。</span><span class="sxs-lookup"><span data-stu-id="e62a1-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="e62a1-107">范围</span><span class="sxs-lookup"><span data-stu-id="e62a1-107">Scope</span></span>|<span data-ttu-id="e62a1-108">边缘</span><span class="sxs-lookup"><span data-stu-id="e62a1-108">Edge</span></span>|
|<span data-ttu-id="e62a1-109">版本</span><span class="sxs-lookup"><span data-stu-id="e62a1-109">Version</span></span>|<span data-ttu-id="e62a1-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e62a1-110">4.6.1</span></span>|
|<span data-ttu-id="e62a1-111">类型</span><span class="sxs-lookup"><span data-stu-id="e62a1-111">Type</span></span>|<span data-ttu-id="e62a1-112">重定目标</span><span class="sxs-lookup"><span data-stu-id="e62a1-112">Retargeting</span></span>|
