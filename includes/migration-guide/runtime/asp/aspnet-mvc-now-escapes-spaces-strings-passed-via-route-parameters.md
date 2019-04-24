---
ms.openlocfilehash: 2278d82d5362fe217ca4bce02a052d4b440843c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774246"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>ASP.NET MVC 现在将转义通过路由参数传递的字符串中的空格

|   |   |
|---|---|
|详细信息|为了遵守 RFC 2396，从路由中填充操作参数时，现在将转义路由路径中的空格。 因此，尽管 <code>/controller/action/some data</code> 之前会匹配路由 <code>/controller/action/{data}</code> 并提供 <code>some data</code> 作为数据参数，但它现在将改为提供 <code>some%20data</code>。|
|建议|应更新代码，以取消转义路由中的字符串参数。 如果需要原始 URI，可通过 <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API 进行访问。|
|范围|次要|
|Version|4.5.2|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|
