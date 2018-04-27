### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>在 .NET Framework 4.5 下序列化的 MailMessage 对象进行反序列化可能会失败

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5 开始，<xref:System.Web.Mail.MailMessage> 对象可以包含非 ASCII 字符。 在 .NET Framework 4 中，仅支持 ASCII 字符。 包含非 ASCII 字符并在 .NET Framework 4.5 或更高版本下序列化的 <xref:System.Web.Mail.MailMessage> 对象不能在 .NET Framework 4 下进行反序列化。|
|建议|请确保在反序列化 <xref:System.Web.Mail.MailMessage> 对象时，代码会提供异常处理。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|

