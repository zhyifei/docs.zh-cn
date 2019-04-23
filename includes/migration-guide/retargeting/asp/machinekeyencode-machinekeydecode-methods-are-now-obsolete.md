---
ms.openlocfilehash: 77e04333ed2b9a5ca8b900c1355fb5b12957772d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774304"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="8fe80-101">MachineKey.Encode 和 MachineKey.Decode 方法现已过时</span><span class="sxs-lookup"><span data-stu-id="8fe80-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8fe80-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="8fe80-102">Details</span></span>|<span data-ttu-id="8fe80-103">这些方法现在已过时。</span><span class="sxs-lookup"><span data-stu-id="8fe80-103">These methods are now obsolete.</span></span> <span data-ttu-id="8fe80-104">调用这些方法的代码编译会产生编译器警告。</span><span class="sxs-lookup"><span data-stu-id="8fe80-104">Compilation of code that calls these methods produces a compiler warning.</span></span>|
|<span data-ttu-id="8fe80-105">建议</span><span class="sxs-lookup"><span data-stu-id="8fe80-105">Suggestion</span></span>|<span data-ttu-id="8fe80-106">建议的替代项为 <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> 和 <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>。</span><span class="sxs-lookup"><span data-stu-id="8fe80-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="8fe80-107">或者，可以禁止显示生成警告，也可以使用较早的编译器避免出现此类警告。</span><span class="sxs-lookup"><span data-stu-id="8fe80-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="8fe80-108">API 仍受支持。</span><span class="sxs-lookup"><span data-stu-id="8fe80-108">The APIs are still supported.</span></span>|
|<span data-ttu-id="8fe80-109">范围</span><span class="sxs-lookup"><span data-stu-id="8fe80-109">Scope</span></span>|<span data-ttu-id="8fe80-110">次要</span><span class="sxs-lookup"><span data-stu-id="8fe80-110">Minor</span></span>|
|<span data-ttu-id="8fe80-111">版本</span><span class="sxs-lookup"><span data-stu-id="8fe80-111">Version</span></span>|<span data-ttu-id="8fe80-112">4.5</span><span class="sxs-lookup"><span data-stu-id="8fe80-112">4.5</span></span>|
|<span data-ttu-id="8fe80-113">类型</span><span class="sxs-lookup"><span data-stu-id="8fe80-113">Type</span></span>|<span data-ttu-id="8fe80-114">重定目标</span><span class="sxs-lookup"><span data-stu-id="8fe80-114">Retargeting</span></span>|
|<span data-ttu-id="8fe80-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="8fe80-115">Affected APIs</span></span>|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|
