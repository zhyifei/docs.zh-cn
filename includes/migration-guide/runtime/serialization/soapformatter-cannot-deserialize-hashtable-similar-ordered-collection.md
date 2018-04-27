### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>SoapFormatter 无法反序列化哈希表和类似有序的集合对象

|   |   |
|---|---|
|详细信息|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> 不保证在一个 .NET Framework 版本下进行序列化的对象能够在其他版本下成功反序列化。 具体而言，某些有序集合（例如 <xref:System.Collections.Hashtable?displayProperty=name>）已在 4.0 和 4.5 中添加了成员，如果这些类型的对象在 .NET 4.5 中进行了序列化，它们在 .NET 4.0 中将无法反序列化。 请注意，如果序列化的数据在同一 .NET Framework 版本中进行序列化和反序列化，将不会发生任何问题。|
|建议|应使用 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> 序列化或 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> 替换 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> 序列化以适应 .NET Framework 的更改。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|

