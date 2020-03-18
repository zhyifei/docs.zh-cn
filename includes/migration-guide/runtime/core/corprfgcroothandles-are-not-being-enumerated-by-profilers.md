---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858394"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="a4fed-101">探查器未枚举 COR_PRF_GC_ROOT_HANDLEs</span><span class="sxs-lookup"><span data-stu-id="a4fed-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a4fed-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="a4fed-102">Details</span></span>|<span data-ttu-id="a4fed-103">在 .NET Framework v4.5.1 中，分析 API <code>RootReferences2()</code> 错误地不会返回 <code>COR_PRF_GC_ROOT_HANDLE</code>（而是返回 <code>COR_PRF_GC_ROOT_OTHER</code>）。</span><span class="sxs-lookup"><span data-stu-id="a4fed-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="a4fed-104">此问题已从 .NET Framework 4.6 开始修复。</span><span class="sxs-lookup"><span data-stu-id="a4fed-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="a4fed-105">建议</span><span class="sxs-lookup"><span data-stu-id="a4fed-105">Suggestion</span></span>|<span data-ttu-id="a4fed-106">此问题已在 .NET Framework 4.6 中解决，因此升级到该版本的 .NET Framework 即可解决该问题。</span><span class="sxs-lookup"><span data-stu-id="a4fed-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="a4fed-107">范围</span><span class="sxs-lookup"><span data-stu-id="a4fed-107">Scope</span></span>|<span data-ttu-id="a4fed-108">次要</span><span class="sxs-lookup"><span data-stu-id="a4fed-108">Minor</span></span>|
|<span data-ttu-id="a4fed-109">Version</span><span class="sxs-lookup"><span data-stu-id="a4fed-109">Version</span></span>|<span data-ttu-id="a4fed-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a4fed-110">4.5.1</span></span>|
|<span data-ttu-id="a4fed-111">类型</span><span class="sxs-lookup"><span data-stu-id="a4fed-111">Type</span></span>|<span data-ttu-id="a4fed-112">运行时</span><span class="sxs-lookup"><span data-stu-id="a4fed-112">Runtime</span></span>|
