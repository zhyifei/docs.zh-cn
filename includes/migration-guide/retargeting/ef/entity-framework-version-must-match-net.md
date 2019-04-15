---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234614"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="9fe3a-101">Entity Framework 版本必须与 .NET Framework 版本匹配</span><span class="sxs-lookup"><span data-stu-id="9fe3a-101">Entity Framework version must match the .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9fe3a-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="9fe3a-102">Details</span></span>|<span data-ttu-id="9fe3a-103">Entity Framework 版本应与 .NET Framework 版本匹配。</span><span class="sxs-lookup"><span data-stu-id="9fe3a-103">The entity framework version should be matched with the .NET framework version.</span></span> <span data-ttu-id="9fe3a-104">Entity Framework 5 推荐用于 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="9fe3a-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="9fe3a-105">在与 <xref:System.ComponentModel.DataAnnotations> 相关的 .NET Framework 4.5 项目中，存在一些已知的 EF 4.x 问题。</span><span class="sxs-lookup"><span data-stu-id="9fe3a-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="9fe3a-106">在 .NET 4.5 中，这些问题被移动到不同的程序集中，所以在确定使用哪些注释时存在问题。</span><span class="sxs-lookup"><span data-stu-id="9fe3a-106">In .NET 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>|
|<span data-ttu-id="9fe3a-107">建议</span><span class="sxs-lookup"><span data-stu-id="9fe3a-107">Suggestion</span></span>|<span data-ttu-id="9fe3a-108">对于 .NET Framework 4.5 升级到 Entity Framework 5</span><span class="sxs-lookup"><span data-stu-id="9fe3a-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>|
|<span data-ttu-id="9fe3a-109">范围</span><span class="sxs-lookup"><span data-stu-id="9fe3a-109">Scope</span></span>|<span data-ttu-id="9fe3a-110">主要</span><span class="sxs-lookup"><span data-stu-id="9fe3a-110">Major</span></span>|
|<span data-ttu-id="9fe3a-111">版本</span><span class="sxs-lookup"><span data-stu-id="9fe3a-111">Version</span></span>|<span data-ttu-id="9fe3a-112">4.5</span><span class="sxs-lookup"><span data-stu-id="9fe3a-112">4.5</span></span>|
|<span data-ttu-id="9fe3a-113">类型</span><span class="sxs-lookup"><span data-stu-id="9fe3a-113">Type</span></span>|<span data-ttu-id="9fe3a-114">重定目标</span><span class="sxs-lookup"><span data-stu-id="9fe3a-114">Retargeting</span></span>|
