---
ms.openlocfilehash: 9d09f598538b9d5ee3f995d6281b8eb4b2668050
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761264"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="af596-101">WPF 拼写检查器引发的 ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="af596-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="af596-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="af596-102">Details</span></span>|<span data-ttu-id="af596-103">应用程序关闭，拼写检查器引发 <xref:System.ObjectDisposedException?displayProperty=name>，在这期间，WPF 应用程序有时会出现故障。</span><span class="sxs-lookup"><span data-stu-id="af596-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="af596-104">.NET Framework 4.7 WPF 中已通过妥善处理异常解决了此问题，因此确保了应用程序不再受到不良影响。</span><span class="sxs-lookup"><span data-stu-id="af596-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="af596-105">应注意，在调试器控制下运行的应用程序中会继续观察到偶尔引发的最可能异常。</span><span class="sxs-lookup"><span data-stu-id="af596-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="af596-106">建议</span><span class="sxs-lookup"><span data-stu-id="af596-106">Suggestion</span></span>|<span data-ttu-id="af596-107">升级到 .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="af596-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="af596-108">范围</span><span class="sxs-lookup"><span data-stu-id="af596-108">Scope</span></span>|<span data-ttu-id="af596-109">边缘</span><span class="sxs-lookup"><span data-stu-id="af596-109">Edge</span></span>|
|<span data-ttu-id="af596-110">版本</span><span class="sxs-lookup"><span data-stu-id="af596-110">Version</span></span>|<span data-ttu-id="af596-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="af596-111">4.6.1</span></span>|
|<span data-ttu-id="af596-112">类型</span><span class="sxs-lookup"><span data-stu-id="af596-112">Type</span></span>|<span data-ttu-id="af596-113">运行时</span><span class="sxs-lookup"><span data-stu-id="af596-113">Runtime</span></span>|

