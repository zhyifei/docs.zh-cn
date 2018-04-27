### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>XmlSchemaException 现在正确设置行位置

|   |   |
|---|---|
|详细信息|如果将 <xref:System.Xml.Linq.LoadOptions.SetLineInfo> 值传递给 Load 方法并发生验证错误，则 <xref:System.Xml.Schema.XmlSchemaException.LineNumber> 和 <xref:System.Xml.Schema.XmlSchemaException.LinePosition> 属性现在包含行信息。|
|建议|应该更新假设不设置 <xref:System.Xml.Schema.XmlSchemaException.LineNumber> 和 <xref:System.Xml.Schema.XmlSchemaException.LinePosition> 的异常处理代码，因为这些属性将会在加载 XML 且使用 SetLineInfo 的时候正确设置。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|

