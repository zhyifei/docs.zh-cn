---
title: "&lt;AppContextSwitchOverrides&gt;元素"
ms.custom: 
ms.date: 01/08/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71888febdc42f0ee65bdcd55a761700eda065bc1
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="ltappcontextswitchoverridesgt-element"></a>&lt;AppContextSwitchOverrides&gt;元素
定义 <xref:System.AppContext> 类使用的一个或多个开关，用于提供新功能的选择退出机制。  
  
 \<configuration>  
 \<运行时 >  
\<AppContextSwitchOverrides >  
  
## <a name="syntax"></a>语法  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`value`|必需的特性。<br /><br /> 定义一个或多个交换机名称和其关联的布尔值。|  
  
### <a name="value-attribute"></a>值属性  
  
|“值”|描述|  
|-----------|-----------------|  
|"名称 = 值"|预定义的开关名称以及其值 (`true`或`false`)。 用分号分隔多个交换机名称/值对 （";"）。 .NET Framework 支持的预定义的开关名称的列表，请参阅备注部分。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 从.NET Framework 4.6，开始`<AppContextSwitchOverrides>`配置文件中的元素允许一个 API，用于确定其应用程序可以充分利用新功能还是保留与以前版本的库兼容性的调用方。 例如，如果 API 的行为已更改的库中的两个版本之间`<AppContextSwitchOverrides>`元素允许选择退出该新行为的库支持的新功能的版本上该 API 的调用方。 用于在.NET Framework 中，调用 Api 的应用程序`<AppContextSwitchOverrides>`元素也可以允许调用方的应用面向要选择加入新功能，如果在包含的.NET Framework 的版本上运行其应用的.NET Framework 的早期版本功能。  
  
 `value`属性`<AppContextSwitchOverrides>`元素包含一个或多个以分号分隔名称/值对组成的单个字符串。  每个名称标识兼容性开关，并且及其对应的值是一个布尔值 (`true`或`false`)，指示开关是否设置。 默认情况下，该交换机是否`false`，和库提供的新功能。 如果此开关设置，它们会仅提供以前的功能 (也就是说，其值是`true`)。 这允许同时允许依赖于以前的行为来选择退出的新功能的调用方提供的现有 API 的新行为的库。  
  
 .NET Framework 支持下列开关：  
  
|交换机名称|描述|引入|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|控制是否 Windows Presentation Foundation 控件布局使用旧算法。 有关详细信息，请参阅[缓解：WPF 布局](~/docs/framework/migration-guide/mitigation-wpf-layout.md)。|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|控制 PackageDigitalSignatureManager 进行签名的包的部件使用的默认算法是 SHA1 或 SHA256。|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|当设置为`false`，允许对使用 Visual Studio 的基于 XAML 的工作流项目进行调试时启用 FIPS。 否则，<xref:System.NullReferenceException>中对 System.Activities 程序集中的方法的调用引发。|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|控制是否在调试器中的工作流实例的校验和使用 MD5 或 SHA1。 | .NET Framework 4.7|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|控件是否<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>方法引发异常时<xref:System.Drawing.Icon>对象具有 PNG 帧。 有关详细信息，请参阅[缓解：图标对象中的 PNG 帧](~/docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md)。|.NET Framework 4.6|  
|`Switch.System.Drawing.Printing.`</br>`OptimizePrintPreview`|控件是否的性能<xref:System.Windows.Forms.PrintPreviewDialog>针对网络打印机进行了优化。 有关详细信息，请参阅[PrintPreviewDialog 控件概述](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)。|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|控制是否异步操作不流从调用线程的上下文。 有关详细信息，请参阅[CurrentCulture 和 CurrentUICulture 穿过了任务](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks)。|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|控件是否<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType>方法尝试仅使用最后一个 DNS 条目的声明类型匹配。 有关详细信息，请参阅[缓解：X509CertificateClaimSet.FindClaims 方法](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)。|.NET Framework 4.6.1|  
|`Switch.System.IO.BlockLongPaths`|控件是否路径长度超过`MAX_PATH`（260 个字符） 引发<xref:System.IO.PathTooLongException>。 有关详细信息，请参阅[长路径支持](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support)。|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|使用反斜杠 ("\\") 而不是正斜杠 （"/"） 中的路径分隔符作为<xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType>属性。 有关详细信息，请参阅[缓解： ZipArchiveEntry.FullName 路径分隔符](~/docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)。|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|控制是否运行系统使用创建的后台线程引发的异常<xref:System.IO.Ports.SerialPort>流终止进程。|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|控制是否使用旧路径规范化和支持 URI 路径<xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType>和<xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>方法。 有关详细信息，请参阅[缓解： 路径规范化](~/docs/framework/migration-guide/mitigation-path-normalization.md)和[缓解： 路径冒号检查](~/docs/framework/migration-guide/mitigation-path-colon-checks.md)。|.NET Framework 4.6.2|  
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|控制是否相等比较的测试<xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType>的一个对象的属性<xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType>的第二个对象的属性。 有关详细信息，请参阅[不正确实现 MemberDescriptor.Equals](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals)。|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|禁用证书增强型密钥用法 (EKU) 对象标识符 (OID) 验证。 增强型密钥用法 (EKU) 扩展为指示使用密钥的应用程序的对象标识符 (Oid) 的集合。|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|通过禁用 SCH_SEND_AUX_RECORD 使用禁用 TLS1.0 浏览器利用针对 SSL/TLS （动物） 缓解。|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|控件是否<xref:System.Net.ServicePointManager?displayProperty=nameWithType>和<xref:System.Net.Security.SslStream?displayProperty=nameWithType>类可以使用 SSL 3.0 协议。 有关详细信息，请参阅[缓解：TLS 协议](~/docs/framework/migration-guide/mitigation-tls-protocols.md)。|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|禁用恢复为默认值为 Tls12、 Tls11、 Tls SystemDefault TLS 版本。|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|禁用 SslStream TLS 服务器端发出警报。|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |控件是否[DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer)序列化基于 ECMAScript V6 和 V8 标准一些控制字符。 有关详细信息，请参阅[缓解：使用 DataContractJsonSerializer 对控制字符进行序列化](Mitigation:%20Serialization%20of%20Control%20Characters%20with%20the%20DataContractJsonSerializer.md)| .NET Framework 4.7 |
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|控件是否<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType>构造函数将设置新的对象的<xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType>具有现有对象引用的属性。 有关详细信息，请参阅[缓解：ClaimsIdentity 构造函数](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md)。|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|控件是否尝试重新使用<xref:System.Security.Cryptography.AesCryptoServiceProvider>解密器引发<xref:System.Security.Cryptography.CryptographicException>。 有关详细信息，请参阅 AesCryptoServiceProvider 解密器提供了可重用 transform](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform)。|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|控件是否的值[CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle)属性是[IntPtr](xref:System.IntPtr) ，表示一个窗口的内存位置处理，或者它是否是窗口句柄 (HWND)。 有关详细信息，请参阅[缓解：应向 CspParameters.ParentWindowHandle 分配 HWND](Mitigation:%20CspParameters.ParentWindowHandle%20Expects%20an%20HWND.md)。 |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|确定某些 SignedCMS 操作的默认值为 SHA1 或 SHA256。 |.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|确定某些？ 1？ 绎操作的默认值为 SHA1 或 SHA256。 |.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|确定是否`TransportWithMessageCredential`安全模式允许带未签名的消息"to"标头。 这是一个可以选择使用的开关。 有关详细信息，请参阅[.NET Framework 4.6.1 中的运行时更改](https://msdn.microsoft.com/library/mt592686.aspx#WCF)。|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|控件是否<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>构造函数引发<xref:System.ArgumentException>如果其中一个元素是`null`。|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|确定是否尝试使用 X509 证书与 CSG 密钥存储提供程序将引发异常。 有关详细信息，请参阅[WCF 传输安全性支持使用 CNG 中存储的证书](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)。|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|因一个线程执行一次的限制可重入服务的实例的句柄死锁。|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|连同`Switch.System.Net.DontEnableSchUseStrongCrypto`，确定 WCF 消息安全是否使用 TLS 1.1 和 TLS 1.2。|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|确定默认的消息签名的 WCF 中的 MSMQ 消息的算法是 SHA1 或 SHA256。|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|控制 WCF 是否使用 SHA1 或 SHA256 哈希来生成随机的命名管道的名称。|.NET Framework 4.7.1|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|控制是否在服务启动时引发的异常会传播到调用方<xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>方法。|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |确定 Windows Presentation Foundation 是否适用旧算法 (`true`) 或新算法 (`false`) 在分配的空间\*的列。 有关详细信息，请参阅[缓解：网格控件向 *-列分配空间](Mitigation:%20Grid%20Control's%20Space%20Allocation%20to%20Star-columns.md)。 |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|是否选择器或选项卡控件始终引发所选内容之前更新其所选的值属性的值的控件更改事件。|.NET Framework 4.7.1|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|允许自定义代码之外 opts<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>实现安全地筛选消息，而不引发异常时<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>调用方法。 有关详细信息，请参阅[缓解：自定义 IMessageFilter.PreFilterMessage 实现](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)。|.NET Framework 4.6.1|  
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|确定是否一个可选`WM_POINTER`-在 WPF 应用程序中启用基于的触摸/触笔堆栈。 有关详细信息，请参阅[缓解： 基于指针的触摸和触笔支持](Mitigation:%20Pointer-based%20Touch%20and%20Stylus%20Support.md) | 
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|控制是否旧式[NullReferenceException](xref:System.NullReferenceException)引发而不是更具体地说就是指示异常原因的异常 (如[DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException)或[FileNotFoundException](xref:System.IO.FileNotFoundException)。 它旨在取决于处理的代码用于[NullReferenceException](xref:System.NullReferenceException)。 | .NET Framework 4.7 |
|`Switch.UseLegacyAccessibilityFeatures`|控件是否可访问性功能可从.NET Framework 4.7.1 开始是启用还是禁用。 | .NET Framework 4.7.1 |
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|控制是否通过 XSD 架构验证忽略空键顺序在复合键。 有关详细信息，请参阅[缓解： XML 架构验证](~/docs/framework/migration-guide/mitigation-xml-schema-validation.md)。|.NET Framework 4.6|  
  
> [!NOTE]
>  而不是添加`AppContextSwitchOverrides`到应用程序配置文件的元素，你还可以设置这些开关以编程方式通过调用`static`（在 C# 中) 或`Shared`（在 Visual Basic)<xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>方法。  
  
 库开发人员还可以定义自定义的开关，以允许调用方来选择退出更改他们的库的更高版本中引入的功能。 有关更多信息，请参见 <xref:System.AppContext> 类。  
  
## <a name="example"></a>示例  
 下面的示例使用`AppContextSwitchOverrides`元素来定义单个应用程序兼容性开关， `Switch.System.Globalization.NoAsyncCurrentCulture`，防止在异步方法调用中的线程之间流动区域性。  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 下面的示例使用`AppContextSwitchOverrides`元素以定义两个应用程序兼容性开关，`Switch.System.Globalization.NoAsyncCurrentCulture`和`Switch.System.IO.BlockLongPaths`。 请注意，用分号分隔的两个名称/值对。  
  
```xml  
<configuration>  
    <runtime>  
       <AppContextSwitchOverrides   
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.AppContext?displayProperty=nameWithType>  
 [\<运行时 > 元素](runtime-element.md)  
 [\<configuration> 元素](../configuration-element.md)
