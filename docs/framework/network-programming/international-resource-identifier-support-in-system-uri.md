---
title: "System.Uri 中的国际资源标识符支持 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# System.Uri 中的国际资源标识符支持
<xref:System.Uri?displayProperty=fullName> 选件类扩展了与国际资源标识符\(IRI\)，和国际化域名\(IDN\)支持。  这些增强功能可在.NET Framework 3.5， 3.0 SP1、2.0 SP1。  
  
## IRI和IDN支持  
 Web地址通常表示使用包含一个非常有限的字符集的统一资源标识符\(uri\) \(URI\):  
  
-   英语字母表中的大写和小写 ASCII 字母。  
  
-   数字 0 到 9。  
  
-   少量其他 ASCII 符号。  
  
 Internet 工程任务组 \(IETF\) 发布的 RFC 2396 和 RFC 3986 中说明了 URI 规范。  
  
 随着 Internet 的发展，越来越需要使用除英语以外的其他语言来标识资源。  能够满足这一需要并允许使用非 ASCII 字符（Unicode\/ISO 10646 字符集中的字符）的标识符称为国际资源标识符 \(IRI\)。  IETF 发布的 RFC 3987 中对 IRI 规范进行了说明。  使用 IRI 可以在 URL 中包含 Unicode 字符。  
  
 现有 <xref:System.Uri?displayProperty=fullName> 选件类扩展提供IRI支持基于RFC 3987。  除非特地启用了 IRI，否则当前用户不会看到 .NET Framework 2.0 的行为发生任何变化。  这确保了应用程序与以前版本的 .NET Framework 的兼容性。  
  
 应用程序是否可以指定使用国际化域名\(IDN\)分析应用于域名，以及是否应该应用IRI分析规则。的。  这可以在 machine.config 或 app.config 文件中完成。  
  
 启用 IDN 会将域名中的所有 Unicode 标签转换为它们的 Punycode 等效项。  Punycode 名称仅包含 ASCII 字符，并且总是以 xn\-\- 前缀开头。  这样做是为了支持 Internet 中现有的 DNS 服务器，因为大多数 DNS 服务器仅支持 ASCII 字符（请参见 RFC 3940）。  
  
 启用 IRI 和 IDN 会影响 <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName> 属性的值。  启用 IRI 和 IDN 还可能更改 <xref:System.Uri.Equals%2A?displayProperty=fullName>、<xref:System.Uri.OriginalString%2A?displayProperty=fullName>、<xref:System.Uri.GetComponents%2A?displayProperty=fullName> 和 <xref:System.Uri.IsWellFormedOriginalString%2A> 方法的行为。  
  
 <xref:System.GenericUriParser?displayProperty=fullName> 类也已经进行了扩展，以便创建支持 IRI 和 IDN 的可自定义的分析器。  通过向 <xref:System.GenericUriParser?displayProperty=fullName> 构造函数传递 <xref:System.GenericUriParserOptions?displayProperty=fullName> 枚举中提供的值的按位组合，可以指定 <xref:System.GenericUriParser?displayProperty=fullName> 对象的行为。  <xref:System.GenericUriParserOptions?displayProperty=fullName> 类型指示分析器支持 RFC 3987 中指定的国际资源标识符 \(IRI\) 语法分析规则。  是否实际使用IRI取决于，如果启用IRI。  
  
 <xref:System.GenericUriParserOptions?displayProperty=fullName> 类型指示分析器支持对主机名进行国际化域名 \(IDN\) 语法分析。  是否实际使用IDN取决于，如果IDN启用。  
  
 启用IRI分析将执行检查根据RFC 3987中的最新IRI规则的规范化和字符。  默认值是为IRI分析禁用，因此规范化和字符检查按照RFC 2396和RFC 3986完成。  
  
 处理在 <xref:System.Uri?displayProperty=fullName> 选件类IRI和IDN也可以控制来设置选件类的 <xref:System.Configuration.IriParsingElement?displayProperty=fullName> 和 <xref:System.Configuration.IdnElement?displayProperty=fullName> 配置。  <xref:System.Configuration.IriParsingElement?displayProperty=fullName> 设置可以启用或禁用 <xref:System.Uri?displayProperty=fullName> 类中的 IRI 处理。  <xref:System.Configuration.IdnElement?displayProperty=fullName> 设置可以启用或禁用 <xref:System.Uri> 类中的 IDN 处理。  <xref:System.Configuration.IriParsingElement?displayProperty=fullName> 设置还可以间接控制 IDN。  若要进行 IDN 处理，必须启用 IRI 处理。  如果禁用了 IRI 处理，则 IDN 处理将设置为默认设置，在此情况下，将使用 .NET Framework 2.0 行为以确保兼容且不使用 IDN 名称。  
  
 ，当第一个 <xref:System.Uri?displayProperty=fullName> 选件类构造，设置为 <xref:System.Configuration.IriParsingElement?displayProperty=fullName> 和 <xref:System.Configuration.IdnElement?displayProperty=fullName> 配置选件类的配置一次将读取。  之后进行的配置设置更改将被忽略。  
  
## 请参阅  
 <xref:System.Configuration.IdnElement?displayProperty=fullName>   
 <xref:System.Configuration.IriParsingElement?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 <xref:System.Uri.DnsSafeHost%2A?displayProperty=fullName>