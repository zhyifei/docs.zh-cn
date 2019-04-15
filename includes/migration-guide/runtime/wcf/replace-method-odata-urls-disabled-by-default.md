---
ms.openlocfilehash: 6dc3669433804a4524c18d5a932f9879343ab508
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235080"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>默认情况下，禁用 OData URL 中的 Replace 方法

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5 开始，默认会禁用 OData URL 中的 Replace 方法。 在禁用 OData Replace 时（现在是默认设置），任何包含 replace 函数的用户请求（这并不常见）都将失败。|
|建议|如果需要 replace 方法（这并不常见），可通过配置设置 (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>) 重新启用。 但是，启用的 replace 方法可能会带来安全漏洞，应仅在仔细检查后使用。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
