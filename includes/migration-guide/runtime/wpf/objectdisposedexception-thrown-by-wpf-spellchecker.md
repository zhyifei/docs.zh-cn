---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774130"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="0ad3a-101">WPF 拼写检查器引发的 ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="0ad3a-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0ad3a-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="0ad3a-102">Details</span></span>|<span data-ttu-id="0ad3a-103">应用程序关闭，拼写检查器引发 <xref:System.ObjectDisposedException?displayProperty=name>，在这期间，WPF 应用程序有时会出现故障。</span><span class="sxs-lookup"><span data-stu-id="0ad3a-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="0ad3a-104">.NET Framework 4.7 WPF 中已通过妥善处理异常解决了此问题，因此确保了应用程序不再受到不良影响。</span><span class="sxs-lookup"><span data-stu-id="0ad3a-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="0ad3a-105">应注意，在调试器控制下运行的应用程序中会继续观察到偶尔引发的最可能异常。</span><span class="sxs-lookup"><span data-stu-id="0ad3a-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="0ad3a-106">建议</span><span class="sxs-lookup"><span data-stu-id="0ad3a-106">Suggestion</span></span>|<span data-ttu-id="0ad3a-107">升级到 .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="0ad3a-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="0ad3a-108">范围</span><span class="sxs-lookup"><span data-stu-id="0ad3a-108">Scope</span></span>|<span data-ttu-id="0ad3a-109">边缘</span><span class="sxs-lookup"><span data-stu-id="0ad3a-109">Edge</span></span>|
|<span data-ttu-id="0ad3a-110">版本</span><span class="sxs-lookup"><span data-stu-id="0ad3a-110">Version</span></span>|<span data-ttu-id="0ad3a-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="0ad3a-111">4.6.1</span></span>|
|<span data-ttu-id="0ad3a-112">类型</span><span class="sxs-lookup"><span data-stu-id="0ad3a-112">Type</span></span>|<span data-ttu-id="0ad3a-113">运行时</span><span class="sxs-lookup"><span data-stu-id="0ad3a-113">Runtime</span></span>|
