### <a name="encoderparameter-ctor-is-obsolete"></a>EncoderParameter ctor 已过时

|   |   |
|---|---|
|详细信息|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> 构造函数现已过时，使用它将引发生成警告。|
|建议|虽然 <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> 构造函数仍将继续运行，但应改用以下构造函数，以避免在使用 .NET 4.5 工具重新编译代码时出现已过时生成警告：<xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>。|
|范围|次要|
|版本|4.5|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|

