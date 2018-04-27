### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>ASP.NET MVC 现在将转义通过路由参数传递的字符串中的空格

|   |   |
|---|---|
|详细信息|为了遵守 RFC 2396，从路由中填充操作参数时，现在将转义路由路径中的空格。 因此，尽管 <code>/controller/action/some data</code> 之前会匹配路由 <code>/controller/action/{data}</code> 并提供 <code>some data</code> 作为数据参数，但它现在将改为提供 <code>some%20data</code>。|
|建议|应更新代码，以取消转义路由中的字符串参数。 如果需要原始 URI，可通过 <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API 进行访问。|
|范围|次要|
|版本|4.5.2|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|

