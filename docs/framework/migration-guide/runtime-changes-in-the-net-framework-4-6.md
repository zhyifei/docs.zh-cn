---
title: ".NET Framework 4.6 中的运行时更改 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5262bcfa-6e48-416b-8972-69cb4002d386
caps.latest.revision: 34
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# .NET Framework 4.6 中的运行时更改
在极少数情况下，运行时更改可能影响面向以前版本的 .NET Framework 但更高版本的 .NET Framework 运行时上运行的现有应用。 他们还包括运行于不同 .NET Framework 运行时环境上的应用程序间的行为差异。 它们包括以下区域中的更改：  
  
-   [核心](#Core)  
  
-   [网络](#Networking)  
  
-   [Windows Presentation Foundation \(WPF\)](#WPF)  
  
-   [安装和部署](#Setup)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [新的 64 位 JIT 编译器](#RyuJIT)  
  
<a name="Core"></a>   
## 核心  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|从 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 开始，<xref:System.Globalization.PersianCalendar> 类均使用回历太阳能算法。|回历太阳能算法将产生与伊朗和阿富汗当前使用的波斯历相同的结果。 对于公历 1800 年到公历 2023 年之间的日期，它还会产生与前一种算法相同的结果。 如果 <xref:System.Globalization.PersianCalendar> 类用于执行日期转换（例如，公历日期与波斯历日期之间的转换）或用于确定某个特定年度是否为闰年，则该范围以外的日期可能会受影响。<br /><br /> 由于此更改，所以安装了 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 的系统的 <xref:System.Globalization.PersianCalendar.MinSupportedDateTime%2A?displayProperty=fullName> 属性值已从 0622 年 3 月 21 更改为 0622 年 3 月 22。<br /><br /> 有关详细信息，请参见<xref:System.Globalization.PersianCalendar>主题。|次要|  
|<xref:System.Runtime.Versioning.TargetFrameworkAttribute>|对于默认应用程序域，除非通过向 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性分配名称进行显式定义，否则 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性的值将派生自 <xref:System.Runtime.Versioning.TargetFrameworkAttribute>（如果存在）。  在之前版本的 .NET Framework 中，除非执行了大量特殊代码路径或创建了非默认应用而没有在 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性中显式指定其目标 Framework，否则 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性的值是 `null`。<br /><br /> 对于非默认应用程序域，确定 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性的值的方法没有更改。 如果没有值显式分配给 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 属性，则非默认应用域将从默认应用程序域继承面向 Framework 的名称。|对于默认应用程序域，<xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 可能会在这前返回 `null` 时返回非空值。 这是希望的行为。|边缘|  
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|如果 .NET Framework 不支持系统上安装的任何证书，则传递一个 `verbose` 参数的 `True` 值会返回一个有效的字符串。 在早期版本的.NET Framework 中，尝试访问不受支持证书的公钥信息有时候会引发异常。|此方法仅用于提供信息 ；该文档说明输出在不同的 .NET Framework 版本中可能并不一定是一致的。 此更改仅影响调用 `ToString(True)` 方法且已安装 .NET Framework 不支持的证书的应用。 通过返回一个字符串而不是引发异常，此更改使该方法更具稳定性。|边缘|  
|反射和分布式 COM \(DCOM\)|反射对象可能无法再从托管代码传道至进程外客户端 下面的类型会受到影响：<xref:System.Reflection.Assembly>；<xref:System.Reflection.MemberInfo> 及其派生类型，包括 <xref:System.Reflection.FieldInfo>、<xref:System.Reflection.MethodInfo>、<xref:System.Type> 和 <xref:System.Reflection.TypeInfo>；<xref:System.Reflection.MethodBody>；<xref:System.Reflection.Module> 和 <xref:System.Reflection.ParameterInfo>。|调用对象的 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707.aspx) 返回 `E_NOINTERFACE`。|次要|  
  
<a name="Networking"></a>   
## 网络  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|<xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> 类的日期和时间值。|若要符合 [RFC822](http://www.ietf.org/rfc/rfc0822.txt) 和 [RFC2822](http://www.ietf.org/rfc/rfc2822.txt)，格式化的日期和时间值现在是具有两位数的小时数。 以前，它在上午 10:00 之前的值为一位数字的小时数。|此更改将影响以下使用方案：<br /><br /> -   在各个 .NET Framework 版本间比较序列化的 <xref:System.Net.Mime.ContentDisposition> 对象的长度或哈希代码。<br />-   在各个 .NET Framework 版本间比较 <xref:System.Net.Mime.ContentDisposition.ToString%2A> 方法的返回值或 <xref:System.Net.Mime.ContentDisposition> 日期和时间属性值的字符串表示形式。|次要|  
  
<a name="WPF"></a>   
## Windows Presentation Foundation \(WPF\)  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|多监视器方案中的窗口呈现|当一个窗口超出多监视器方案中的某个显示屏时，会不经剪辑就呈现整个窗口。|请参阅 [缓解：WPF 窗口呈现](../../../docs/framework/migration-guide/mitigation-wpf-window-rendering.md)。|次要|  
|支持 WPF 文本的控件上的拼写检查器|在 Windows 10 上运行时，拼写检查器可能不会工作，因为平台拼写检查功能仅适用于输入语言列表中存在的语言。|在 Windows 10 中，可用键盘列表中增加了一种语言，Windows 自动下载并安装相应的功能按需 \(FOD\) 包，以提供拼写检查功能。 通过将语言添加到输入语言列表，将支持拼写检查器。|次要|  
  
<a name="Setup"></a>   
## 安装和部署  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|产品版本控制|产品版本控制已从早期版本的 .NET Framework 进行了更改，特别是 .NET Framework 4、4.5、4.5.1 和 4.5.2。 有关详细信息，请参阅[缓解操作：产品版本控制](../../../docs/framework/migration-guide/mitigation-product-versioning.md)。|请参阅 [缓解操作：产品版本控制](../../../docs/framework/migration-guide/mitigation-product-versioning.md)。|中|  
  
<a name="ClickOnce"></a>   
## ClickOnce  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|通过 ClickOnce 使用 SHA\-256 代码签名证书发布的应用。|面向 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 或早期版本的 ClickOnce 应用均采用 SHA\-256 证书签名，在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 或更高版本上不再依赖运行时。|以前，对面向 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 或带 SHA\-256 证书的早期版本的 ClickOnce 应用签名，需要在目标系统上安装 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 或更高版本。 如果没有安装，将导致错误。 此更改移除了该依赖性，并允许将 SHA\-256 证书用于为面向 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 或早期版本的 ClickOnce 应用签名。|次要|  
  
<a name="RyuJIT"></a>   
## 新的 64 位 JIT 编译器  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|异常处理（从 `try` 区域返回）|与旧的 JIT64 实时编译器不同，新的 64 位 JIT 编译器不允许在 `try` 区域中使用 IL [ret](http://msdn.microsoft.com/library/system.reflection.emit.opcodes.ret.aspx) 指令。|ECMA\-335 规范不允许从 `try` 区域返回，并且没有已知的托管编译器会生成此类 IL。 但是，如果由反射发出生成，则 JIT64 编译器执行此类 IL。|边缘|