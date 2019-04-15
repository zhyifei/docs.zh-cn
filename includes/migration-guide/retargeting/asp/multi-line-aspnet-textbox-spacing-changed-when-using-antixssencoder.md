---
ms.openlocfilehash: e2bca42daebd25667ab2f312d5e59089b986503c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234607"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>使用 AntiXSSEncoder 时，多行 ASP.Net 文本框间距已更改

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.0 中，如果使用 <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>，则多余行将插入回发的多行文本框中的各行之间。 在 .NET Framework 4.5 中，不包括这些多余的换行符，仅在 Web 应用面向 .NET Framework 4.5 时才可包含|
|建议|请注意，重定向到 .NET Framework 4.5 的 4.0 Web 应用可能改进了多行文本框，从而不再插入多余的换行符。 如果不需要这样做，当应用在 .NET Framework 4.5 上运行时，通过面向 .NET Framework 4.0 可使用旧行为。|
|范围|次要|
|版本|4.5|
|类型|重定目标|
