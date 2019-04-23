---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774301"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="0a69c-101">Entity Framework 版本必须与 .NET Framework 版本匹配</span><span class="sxs-lookup"><span data-stu-id="0a69c-101">Entity Framework version must match the .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0a69c-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="0a69c-102">Details</span></span>|<span data-ttu-id="0a69c-103">Entity Framework 版本应与 .NET Framework 版本匹配。</span><span class="sxs-lookup"><span data-stu-id="0a69c-103">The entity framework version should be matched with the .NET framework version.</span></span> <span data-ttu-id="0a69c-104">Entity Framework 5 推荐用于 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="0a69c-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="0a69c-105">在与 <xref:System.ComponentModel.DataAnnotations> 相关的 .NET Framework 4.5 项目中，存在一些已知的 EF 4.x 问题。</span><span class="sxs-lookup"><span data-stu-id="0a69c-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="0a69c-106">在 .NET 4.5 中，这些问题被移动到不同的程序集中，所以在确定使用哪些注释时存在问题。</span><span class="sxs-lookup"><span data-stu-id="0a69c-106">In .NET 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>|
|<span data-ttu-id="0a69c-107">建议</span><span class="sxs-lookup"><span data-stu-id="0a69c-107">Suggestion</span></span>|<span data-ttu-id="0a69c-108">对于 .NET Framework 4.5 升级到 Entity Framework 5</span><span class="sxs-lookup"><span data-stu-id="0a69c-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>|
|<span data-ttu-id="0a69c-109">范围</span><span class="sxs-lookup"><span data-stu-id="0a69c-109">Scope</span></span>|<span data-ttu-id="0a69c-110">主要</span><span class="sxs-lookup"><span data-stu-id="0a69c-110">Major</span></span>|
|<span data-ttu-id="0a69c-111">版本</span><span class="sxs-lookup"><span data-stu-id="0a69c-111">Version</span></span>|<span data-ttu-id="0a69c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0a69c-112">4.5</span></span>|
|<span data-ttu-id="0a69c-113">类型</span><span class="sxs-lookup"><span data-stu-id="0a69c-113">Type</span></span>|<span data-ttu-id="0a69c-114">重定目标</span><span class="sxs-lookup"><span data-stu-id="0a69c-114">Retargeting</span></span>|
