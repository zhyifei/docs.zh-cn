### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a>在 .NET Framework 4.5 中使用 NetDataContractSerializer 序列化的 ConcurrentDictionary 无法通过 .NET Framework 4.5.1 或 4.5.2 反序列化

|   |   |
|---|---|
|详细信息|由于对类型作了内部更改，因此在 .NET Framework 4.5 中使用 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> 序列化的 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象无法在 .NET Framework 4.5.1 或 .NET Framework 4.5.2 中反序列化。注意，反之则可行（可以通过 .NET Framework 4.5.x 序列化，然后通过 .NET Framework 4.5 反序列化）。 同样，使用 .NET Framework 4.6 可以实现所有 4.x 的跨版本序列化，单个版本的 .NET Framework 的序列化和反序列化不受影响。|
|建议|如果必须在 .NET Framework 4.5 和 .NET Framework 4.5.1/4.5.2 之间序列化和反序列化 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name>，则应使用备用序列化程序（例如 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> 或 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> 序列化程序）而不是 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>。或者，由于此问题已在 .NET Framework 4.6 中解决，因此升级件到该版本的 .NET Framework 即可解决该问题。|
|范围|次要|
|版本|4.5.1|
|类型|运行时|

