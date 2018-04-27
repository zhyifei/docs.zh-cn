### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttribute 在 WinMD 方案中导出为 ObsoleteAttribute 和 DeprecatedAttribute

|   |   |
|---|---|
|详细信息|创建 Windows 元数据库（.winmd 文件）时，<xref:System.ObsoleteAttribute?displayProperty=name> 属性将导出为 <xref:System.ObsoleteAttribute?displayProperty=name> 和 [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute)。|
|建议|重新编译使用 <xref:System.ObsoleteAttribute?displayProperty=name> 属性的现有源代码可能会在从 C++/CX 或 JavaScript 使用该代码时生成警告。我们不建议将 <xref:System.ObsoleteAttribute?displayProperty=name> 和 [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) 同时用于托管程序集中的代码，这可能会导致生成警告。|
|范围|边缘|
|版本|4.5.1|
|类型|重定目标|

