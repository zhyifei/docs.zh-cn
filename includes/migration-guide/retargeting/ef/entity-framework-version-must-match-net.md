---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234614"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a>Entity Framework 版本必须与 .NET Framework 版本匹配

|   |   |
|---|---|
|详细信息|Entity Framework 版本应与 .NET Framework 版本匹配。 Entity Framework 5 推荐用于 .NET Framework 4.5。 在与 <xref:System.ComponentModel.DataAnnotations> 相关的 .NET Framework 4.5 项目中，存在一些已知的 EF 4.x 问题。 在 .NET 4.5 中，这些问题被移动到不同的程序集中，所以在确定使用哪些注释时存在问题。|
|建议|对于 .NET Framework 4.5 升级到 Entity Framework 5|
|范围|主要|
|版本|4.5|
|类型|重定目标|
