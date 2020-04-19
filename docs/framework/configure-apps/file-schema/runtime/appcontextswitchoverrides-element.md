---
title: 应用上下文切换覆盖元素
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: 95ae438e9fb52cc584d18a981bffb66147eb4a77
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242811"
---
# <a name="appcontextswitchoverrides-element"></a>\<应用上下文切换覆盖>元素

定义 <xref:System.AppContext> 类使用的一个或多个开关，用于提供新功能的选择退出机制。

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<应用上下文切换覆盖>**

## <a name="syntax"></a>语法

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>特性和元素
 下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

|特性|描述|
|---------------|-----------------|
|`value`|必需的特性。<br /><br /> 定义一个或多个交换机名称及其关联的布尔值。|

### <a name="value-attribute"></a>值属性

|“值”|说明|
|-----------|-----------------|
|"名称=值"|预定义的开关名称及其值 （`true`或`false`。 多个开关名称/值对由分号分隔（";"）。 有关 .NET Framework 支持的预定义交换机名称的列表，请参阅备注部分。|

### <a name="child-elements"></a>子元素
 无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|
|`runtime`|包含有关运行时初始化选项的信息。|

## <a name="remarks"></a>备注
 从 .NET Framework 4.6`<AppContextSwitchOverrides>`开始，配置文件中的元素允许 API 调用方确定其应用是否可以利用新功能或保留与库的早期版本的兼容性。 例如，如果 API 的行为在库的两个版本之间发生更改，则`<AppContextSwitchOverrides>`该元素允许该 API 的调用方选择退出支持新功能的库版本上的新行为。 对于在 .NET 框架中调用 API 的应用`<AppContextSwitchOverrides>`，如果应用在包含该功能的 .NET Framework 版本上运行，则该元素还可以允许应用以早期版本的 .NET Framework 为目标的调用方选择加入新功能。

 `<AppContextSwitchOverrides>`元素`value`的属性由一个字符串组成，该字符串由一个或多个分号分隔的名称/值对组成。  每个名称标识兼容性开关，其相应的值是布尔 （`true`或`false`）， 指示是否设置了该开关。 默认情况下，开关为`false`，库提供新功能。 仅当设置开关（即其值为`true`）时，它们才提供以前的功能。 这允许库为现有 API 提供新的行为，同时允许依赖于前一个行为的调用方选择退出新功能。

 .NET 框架支持以下交换机：

|切换名称|说明|介绍|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|控制 Windows 演示文稿基础是否使用旧算法进行控件布局。 有关详细信息，请参阅[缓解：WPF 布局](../../../migration-guide/mitigation-wpf-layout.md)。|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|控制用于由包数字签名管理器对包部件进行签名的默认算法是 SHA1 还是 SHA256。<br>由于与 SHA1 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|设置为 时`false`，允许在启用 FIPS 时使用 Visual Studio 使用基于 XAML 的工作流项目进行调试。 如果没有它，将<xref:System.NullReferenceException>引发对 System 中方法的调用。|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|控制调试器中工作流实例的校验和是使用 MD5 还是 SHA1。 | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|控制工作流校验和哈希是使用在 .NET 框架 4.7 （）`true`中作为默认值引入的 SHA1 算法，还是使用在 .NET 框架 4.8 （）`false`中作为默认值引入的默认 SHA256 算法。<br>由于与 SHA1 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|控制使用便携式 PDB 时获取的堆栈跟踪是否可以包括源文件和行信息。 `false`包括源文件和行信息;否则， `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|控制当<xref:System.Drawing.Icon>对象<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>具有 PNG 帧时，该方法是否引发异常。 有关详细信息，请参阅[缓解：图标对象中的 PNG 帧](../../../migration-guide/mitigation-png-frames-in-icon-objects.md)。|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|确定<xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>对象<xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType>在方法添加到集合时是否正确释放。 `true`维护旧行为;`false`处置所有私有字体对象。 |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|控制 是否针对网络打印机<xref:System.Windows.Forms.PrintPreviewDialog>优化 了 的性能。 有关详细信息，请参阅[打印预览对话框控件概述](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)。|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|控制是否对日本日历时执行年份范围检查。 `true`强制执行年份范围检查，并`false`禁用它们（默认行为）。 有关详细信息，请参阅[使用日历](../../../../standard/datetime/working-with-calendars.md)。|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|控制在分析操作中是否仅识别"1"是日本日历时代的第一年。 `true`只识别"1";`false`以识别"1"或"甘宁"（默认行为）。 有关详细信息，请参阅[使用日历](../../../../standard/datetime/working-with-calendars.md)。|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|控制日本日历时代的第一年在格式操作中是否表示为"1"或 Gannen。 `true`将那个时代的第一年格式化为"1";`false`将其格式化为"甘宁"（默认行为）。 有关详细信息，请参阅[使用日历](../../../../standard/datetime/working-with-calendars.md)。|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|控制异步操作是否不从调用线程的上下文流。 有关详细信息，请参阅[当前文化和当前 UI 文化跨任务流](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks)。|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|控制<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType>该方法是否尝试仅将声明类型与最后一个 DNS 条目匹配。 有关详细信息，请参阅[缓解：X509CertificateClaimSet.FindClaims 方法](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)。|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|控制是否允许授权上下文.empty 返回可变对象。|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|控制路径是否长于`MAX_PATH`（260 个字符）<xref:System.IO.PathTooLongException>引发 。 有关详细信息，请参阅[长路径支持](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support)。|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|控制本机操作系统例程是否用于<xref:System.IO.Compression.DeflateStream>类的解压缩。 `false`使用本机 API;`true`使用实现<xref:System.IO.Compression.DeflateStream>。|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|使用反斜杠 （""）\\而不是前斜杠 （"/"） 作为属性中的<xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType>路径分隔符。 有关详细信息，请参阅[缓解：ZipArchiveEntry.全名路径分隔符](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)。|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|控制在使用<xref:System.IO.Ports.SerialPort>流创建的后台线程上引发的操作系统异常是否终止进程。|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|控制是否使用旧路径规范化，<xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType>以及 和<xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>方法是否支持 URI 路径。 有关详细信息，请参阅[缓解：路径规范化](../../../migration-guide/mitigation-path-normalization.md)和[缓解：路径冒号检查](../../../migration-guide/mitigation-path-colon-checks.md)。|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|控制相等性测试是否将一个<xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType>对象的属性与第二个<xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType>对象的属性进行比较。 有关详细信息，请参阅[成员描述符的不正确实现。](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals)|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|禁用证书增强密钥使用 （EKU） 对象标识符 （OID） 验证。 增强型密钥使用 (EKU) 扩展是指示使用密钥的应用程序的对象标识符 (OID) 的集合。|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|禁用 TLS1.0 浏览器漏洞攻击 SSL/TLS （BEAST） 缓解通过禁用使用SCH_SEND_AUX_RECORD。|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|控制 和<xref:System.Net.ServicePointManager?displayProperty=nameWithType><xref:System.Net.Security.SslStream?displayProperty=nameWithType>类是否可以使用 SSL 3.0 协议。 有关详细信息，请参阅[缓解：TLS 协议](../../../migration-guide/mitigation-tls-protocols.md)。|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|禁用系统默认 TLS 版本，恢复到默认值 Tls12、Tls11、Tls。|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|禁用 SslStream TLS 服务器端警报。|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|控制是禁用 COM 互通事件中的 ByRef SafeArray 参数封`false`送回本机代码 （ ）， 还是禁用封`true`送回本机代码 （ ）|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |控制[DataContractJon 序列化器](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer)是否基于 ECMAScript V6 和 V8 标准序列化某些控制字符。 有关详细信息，请参阅[缓解：使用 DataContractJsonSerializer 对控制字符进行序列化](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|控制 是<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>支持多个调整还是仅支持时区的单个调整。 如果`true`，它使用<xref:System.TimeZoneInfo>类型来序列化和反序列化日期和时间数据;如果 ，则使用 类型对日期和时间数据进行序列化和非序列化。否则，它使用<xref:System.TimeZone>类型，不支持多个调整规则。|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|控制在<xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType>对象序列化和反序列化期间是否使用较大的数组大小。 将此开关设置为`true`按 类型（如<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>） 提高大型对象图形的序列化和反序列化性能。 |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|控制<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29>构造函数是否使用现有对象引用设置新对象<xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType>的属性。 有关详细信息，请参阅[缓解：ClaimsIdentity 构造函数](../../../migration-guide/retargeting/4.6.1-4.6.2.md)。|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|控制是否尝试重用<xref:System.Security.Cryptography.AesCryptoServiceProvider>解密器引发 。 <xref:System.Security.Cryptography.CryptographicException> 有关详细信息，请参阅[AesCryptoService 提供程序解密器提供可重用的转换](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform)。|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|控制[Csp参数.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle)属性的值是表示窗口句柄的内存位置的[IntPtr，](xref:System.IntPtr)还是窗口句柄（HWND）。 有关详细信息，请参阅[缓解：应向 CspParameters.ParentWindowHandle 分配 HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value)。 |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|控制在 FIPS 模式下使用托管加密类是引发 （ <xref:System.Security.Cryptography.CryptographicException> `true`） 还是依赖于系统库 （ ）`false`的实现 。|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|确定某些已签名 CMS 操作的默认值是 SHA1 还是 SHA256。<br>由于与 SHA1 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|控制<xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType>该方法是否正确处理操作系统支持的所有命名曲线 （`false`） 或还原为旧行为。|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|确定某些已签名XML操作的默认值是 SHA1 还是 SHA256。<br>由于与 SHA1 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|确定`TransportWithMessageCredential`安全模式是否允许具有未签名"to"标头的邮件。 这是一个选择加入开关。 有关详细信息，请参阅[.NET 框架 4.6.1 中的运行时更改](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf)。|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|控制<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>构造函数是否引发 ，<xref:System.ArgumentException>如果其中一个元素是`null`。|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|确定尝试将 X509 证书与 CSG 密钥存储提供程序一起引发异常。 有关详细信息，请参阅[WCF 传输安全支持使用 CNG 存储的证书](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)。|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|将 HTTP 传输与自托管服务一起使用时，将此值设置为`true`使 WCF 忽略将`Connection: close`标头添加到请求的响应标头的应用程序。 将此值设置为`false`启用将`Connection: close`标头添加到响应标头，从而导致在发送响应后关闭请求套接字。|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|处理将重新进入服务的实例限制为一次执行单个线程而导致的死锁。|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|与`Switch.System.Net.DontEnableSchUseStrongCrypto`一起，确定 WCF 消息安全性是否使用 TLS 1.1 和 TLS 1.2。|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|的值`false`设置默认配置以允许操作系统选择协议。 的值`true`将默认值设置为可用的最高协议。 （也可在以前框架版本的服务分支上提供）|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|确定 WCF 中 MSMQ 消息的默认消息签名算法是 SHA1 还是 SHA256。<br>由于与 SHA1 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|控制 WCF 是使用 SHA1 还是 SHA256 哈希来为命名管道生成随机名称。<br>由于与 SHA1 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|控制在异常消息为空时是否引发[空引用异常](xref:System.NullReferenceException)。|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|控制服务启动时引发的异常是否传播到<xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>方法的调用方。|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|控制实例<xref:System.Threading.Timer>是否利用大规模环境的性能改进。 如果`true`启用 了 性能改进;如果启用了 性能改进。如果`false`（默认值），则禁用它们。|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|确定有时解码的某些百分比编码字符现在是否始终保持编码。 如果`true`解码，则它们被解码;否则， `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|确定 URI 中单向字符的处理。 `true`将它们从 URI 中剥离;`false`保留它们并将其编码百分比。|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |确定 Windows 演示文稿基础在将空间分配给`true`\*列时是否应用旧算法`false`（ ） 或新算法 （ ）。 有关详细信息，请参阅[缓解：网格控件向 *-列分配空间](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns)。 |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|控制选择器或制表符控件在引发选择更改的事件之前是否始终更新其所选值属性的值。|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|确定非基于 Adorner 的选择呈现是否可用于<xref:System.Windows.Controls.TextBox>和<xref:System.Windows.Controls.PasswordBox>控件以防止被遮挡的文本 （），`false`或者文本是否仅在 Adorner 图层 （）`true`中呈现。|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|控制<xref:System.Windows.Data.Binding?displayProperty=nameWithType>类使用不当的自定义 IList 索引器`true`（ ）`false`还是正确 （ ） 。|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|确定 DPI 更改是按系统（的值为`false`） 还是基于每个监视器（值的值`true`） 发生。|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|控制是否<xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType>禁用 （）`true`或启用`false`了在|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|确定开发人员是否需要在存在控件文本时专门<xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>处理操作。 `true`处理操作<xref:System.Windows.Forms.DomainUpDown.UpButton>;`false`和<xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>操作要正确<xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>同步。|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|选择退出允许自定义<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>实现安全地筛选消息的代码，而不会在调用<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>方法时引发异常。 有关详细信息，请参阅[缓解：自定义 IMessageFilter.PreFilterMessage 实现](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)。|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|确定当用户从<xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>嵌套<xref:System.Windows.Forms.ToolStripMenuItem>控件打开菜单时，属性是否返回源代码管理。 `true`返回`null`，遗留行为;`false`返回源代码管理。|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|控制工具提示调用支持是禁用 （`true`） 还是启用`false`（ 。 启用工具提示调用`Switch.UseLegacyAccessibilityFeatures`支持还需要由 定义的旧式辅助功能`Switch.UseLegacyAccessibilityFeatures.2`，并且`Switch.UseLegacyAccessibilityFeatures.3`所有功能都已禁用（设置为`false`）。|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|确定是否在`WM_POINTER`WPF 应用程序中启用了可选的基于触摸/手写的堆栈。 有关详细信息，请参阅[缓解：基于指针的触摸和手写笔支持](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|确定用于校验和的默认哈希算法是 SHA256 （`false`） 还是`true`SHA1 （）。<br>由于与 SHA1 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|控制是否引发旧版[NullReferenceException，](xref:System.NullReferenceException)而不是更具体地指示异常原因的异常（如[目录未找到Exception](xref:System.IO.DirectoryNotFoundException)或[FileNotFoundexception](xref:System.IO.FileNotFoundException)）。 它供依赖于处理[Nullreferenceexception](xref:System.NullReferenceException)的代码使用。 | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|控制工作流项目生成中 XOML 文件的校验和哈希是使用 MD5`true`算法 （），还是使用在 .NET 框架 4.8 中作为默认值引入的 SHA256 算法。<br>由于与 MD5 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|控制 SqlTrackIngService 的校验和哈希是使用 MD5`true`算法 （ ） 进行缓存的字符串，还是使用作为 .NET 框架 4.8 中的默认值引入的 SHA256 算法。<br>由于与 MD5 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|控制工作流运行时的校验和哈希是使用 MD5 算法 （`true`） 进行缓存的工作流定义，还是使用作为 .NET 框架 4.8 中的默认值引入的 SHA256 算法。<br>由于与 MD5 冲突，Microsoft 建议使用 SHA256。|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|控制以 .NET 框架 4.7.1 开头的可用辅助功能是启用还是禁用。 | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|控制 .NET 框架 4.7.2 中可用的辅助功能`false`是启用 （`true`） 还是禁用 （ 。 `Switch.UseLegacyAccessibilityFeatures`如果`true`还必须启用`true`.NET 框架 4.7.1 辅助功能。|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|控制 .NET 框架 4.8 中引入的辅助`false`功能是启用`true`（ ） 还是禁用 （ 。 如果`true` `Switch.UseLegacyAccessibilityFeatures` ，`Switch.UseLegacyAccessibilityFeatures.2`也必须为`true`。|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|控制当用户将鼠标光标悬停在 WPF 控件 （） 上时，还是`true`显示工具提示，或者它们是否同时显示在键盘焦点上，是否通过键盘`false`快捷键 （，默认行为） 显示。 对于在 .NET Framework 4.8 上运行但针对 .NET Framework 的早期版本的应用程序，启用键盘焦点和快捷键`Switch.UseLegacyAccessibilityFeatures`支持`Switch.UseLegacyAccessibilityFeatures.2`都需要`Switch.UseLegacyAccessibilityFeatures.3`将 和`false`都设置为 。|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|控制 XSD 架构验证是否忽略复合键中的空键序列。 有关详细信息，请参阅[缓解：XML 架构验证](../../../migration-guide/mitigation-xml-schema-validation.md)。|.NET Framework 4.6|

> [!NOTE]
> 还可以通过调用`AppContextSwitchOverrides``static`（在 C# 中）或`Shared`（在 Visual Basic 中）<xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>方法以编程方式设置交换机，而不是将元素添加到应用程序配置文件中。

 库开发人员还可以定义自定义交换机，以允许调用方选择退出其库的更高版本中引入的已更改功能。 有关更多信息，请参见 <xref:System.AppContext> 类。

## <a name="switches-in-aspnet-applications"></a>ASP.NET应用中的交换机

通过将[\<>](../appsettings/add-element-for-appsettings.md)元素添加到 Web.config 文件[\<的应用设置>](../appsettings/index.md)部分，可以将ASP.NET应用程序配置为使用兼容性设置。

下面的示例使用 元素`<add>`向 Web.config`<appSettings>`文件的部分添加两个设置：

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>示例

 下面的示例使用 元素`AppContextSwitchOverrides`定义单个应用程序兼容性开关 ，`Switch.System.Globalization.NoAsyncCurrentCulture`以防止区域性在异步方法调用中跨线程流动。

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 下面的示例使用 元素`AppContextSwitchOverrides`定义两个应用程序兼容性开关 和`Switch.System.Globalization.NoAsyncCurrentCulture``Switch.System.IO.BlockLongPaths`。 分号分隔两个名称/值对。

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>另请参阅

- <xref:System.AppContext?displayProperty=nameWithType>
- [\<运行时>元素](runtime-element.md)
- [\<配置>元素](../configuration-element.md)
