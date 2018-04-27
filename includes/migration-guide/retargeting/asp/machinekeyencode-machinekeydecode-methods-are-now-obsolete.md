### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>MachineKey.Encode 和 MachineKey.Decode 方法现已过时

|   |   |
|---|---|
|详细信息|这些方法现在已过时。 调用这些方法的代码编译会产生编译器警告。|
|建议|建议的替代项为 <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> 和 <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>。 或者，可以禁止显示生成警告，也可以使用较早的编译器避免出现此类警告。 API 仍受支持。|
|范围|次要|
|版本|4.5|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|

