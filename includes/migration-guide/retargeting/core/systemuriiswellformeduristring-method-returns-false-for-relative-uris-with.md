---
ms.openlocfilehash: 734041f5921571cd11225a359e794526cbd8d0e1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234605"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a>System.Uri.IsWellFormedUriString 方法为第一个段中具有冒号字符型的相对 URI 返回 false

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5 开始，<xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> 会将第一个段中带有 <code>:</code> 的相对 URI 视为格式不正确。 这是 .NET Framework 4.0 中 <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> 行为的更改，以符合 RFC3986。|
|建议|此更改（与许多其他 URI 更改一样）仅影响以 .NET Framework 4.5（或更高版本）为目标的应用程序。 要继续使用旧行为，请使应用以 .NET Framework 4.0 为目标。 或者，调用 <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> 前扫描 URI，查找出于验证目的想要删除的 <code>:</code> 字符（如果旧行为是可取的）。|
|范围|次要|
|版本|4.5|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType></li></ul>|
