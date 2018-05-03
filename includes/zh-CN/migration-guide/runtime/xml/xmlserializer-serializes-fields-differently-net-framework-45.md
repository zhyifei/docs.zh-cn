### <a name="xmlserializer-serializes-fields-differently-in-net-framework-45"></a>XmlSerializer 在 .NET Framework 4.5 中以不同方式序列化字段

|   |   |
|---|---|
|详细信息|.NET Framework 4.5 中的 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> 更改会导致字段在序列化的 XML 中格式不同。|
|建议|此行为已在 .NET Framework 4.5 的服务更新中更正。 请更新 .NET Framework 4.5，或升级到 .NET Framework 4.5.1 或更高版本，以解决此问题。 或者，以下配置设置将还原为 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> 行为：<pre><code>&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>|
|范围|主要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream%2CSystem.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter%2CSystem.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object%2CSystem.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces%2CSystem.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter%2CSystem.Object%2CSystem.Xml.Serialization.XmlSerializerNamespaces%2CSystem.String%2CSystem.String)?displayProperty=nameWithType></li></ul>|

