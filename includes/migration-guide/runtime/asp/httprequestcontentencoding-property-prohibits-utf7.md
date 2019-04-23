---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803333"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>HttpRequest.ContentEncoding 属性禁止使用 UTF7

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5 开始，<xref:System.Web.HttpRequest?displayProperty=name> 正文禁止使用 UTF-7 编码。 在某些情况下，取决于传入的 UTF-7 数据的应用程序数据将不会正确解码。|
|建议|理想情况下，应更新应用程序，使其在 <xref:System.Web.HttpRequest?displayProperty=name> 中不使用 UTF-7 编码。 或者，可以使用 [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) 元素的 <code>aspnet:AllowUtf7RequestContentEncoding</code> 属性还原旧行为。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
