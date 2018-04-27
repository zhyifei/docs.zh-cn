### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a>探查器未枚举 COR_PRF_GC_ROOT_HANDLEs

|   |   |
|---|---|
|详细信息|在 .NET Framework v4.5.1 中，分析 API <code>RootReferences2()</code> 错误地不会返回 <code>COR_PRF_GC_ROOT_HANDLE</code>（而是返回 <code>COR_PRF_GC_ROOT_OTHER</code>）。 此问题已从 .NET Framework 4.6 开始修复。|
|建议|此问题已在 .NET Framework 4.6 中解决，因此升级到该版本的 .NET Framework 即可解决该问题。|
|范围|次要|
|版本|4.5.1|
|类型|运行时|

