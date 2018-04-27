### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue&lt;T&gt;.TryPeek 可通过 out 参数返回错误的 null

|   |   |
|---|---|
|详细信息|在某些多线程情况下，<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> 可返回 true，但使用 null 值填充 Out 参数（而非正确的扫视值）。|
|建议|此问题已在 .NET Framework 4.5.1 中解决。 升级到该 Framework 即可解决该问题。|
|范围|主要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|

