---
title: ".NET Framework 4.5 中的应用程序兼容性 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility, .NET Framework
- breaking changes [.NET Framework]
ms.assetid: 5c50747c-806c-44a9-ac58-5bbe12a284fa
caps.latest.revision: 76
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 19006cc5f24ffc66b92e53e8174c6bd33c249679
ms.openlocfilehash: 5f63c3217b6def96240447501247d22a1058cacf
ms.lasthandoff: 04/18/2017

---
# <a name="application-compatibility-in-the-net-framework-45"></a>.NET Framework 4.5 中的应用程序兼容性
本主题描述 .NET Framework 4 和 4.5 之间的应用程序兼容性问题，包括基于客户反馈的修复和更改。 这些更改中的大多数更改不需要在应用程序中进行任何编程修改。 有关可能涉及这些修改的更改，请参阅表的“影响”一列。  
  
> [!IMPORTANT]
>  请注意，[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 上不支持模式 [!INCLUDE[winxp](../../../includes/winxp-md.md)]。  
  
 若要了解 .NET Framework 4.5 与 4.5.1 之间的兼容性问题，请参阅 [4.5.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)。  
  
 本主题描述以下几个方面的重大更改：  
  
-   [核心](#core)  
  
-   [Data](#sql)  
  
-   [网络连接](#network)  
  
-   [序列化](#serialize)  
  
-   [打印](#Printing)  
  
-   [工具和资源](#tools)  
  
-   [ASP.NET 2.0](#asp)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Managed Extensibility Framework (MEF)](#mef)  
  
-   [Web 应用程序](#web)  
  
-   [Windows Communication Foundation (WCF)](#wcf)  
  
-   [Windows 窗体](#winForms)  
  
-   [Windows Presentation Foundation (WPF)](#wpf)  
  
-   [Windows Workflow Foundation (WF)](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md#wwf)  
  
-   [XML、XSLT](#xml)  
  
 本主题不讨论 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中已宣布过时的类型和成员。 有关这些类型和成员的列表，请参阅[类库中过时的内容](../../../docs/framework/whats-new/whats-obsolete.md)。 若要了解新增功能，请参阅[新增功能](../../../docs/framework/whats-new/index.md)。  
  
<a name="core"></a>   
## <a name="core"></a>核心  
 除了下面的应用程序兼容性问题外，请参阅[序列化](#serialize)部分，了解与序列化相关的问题。  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName> 和 <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A?displayProperty=fullName> 方法|<xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%28System.Collections.Concurrent.BlockingCollection%7B%600%7D%5B%5D%2C%600%40%29?displayProperty=fullName> 方法不再返回 -1 或抛出异常。 当集合之一被标记为已完成时，<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A?displayProperty=fullName> 方法不再抛出异常。|当其中一个集合为空或已完成，但其他集合仍具有可检索的项时，可通过此更改来使用这些集合。|  
|<xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=fullName>|如果已编译的正则表达式的程序集使用 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 生成但却面向 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]，则在安装了 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 的系统上尝试使用该程序集的正则表达式之一时，将引发异常。|若要解决此问题，可执行下列操作之一：<br /><br /> 使用 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 生成包含正则表达式的程序集。<br /><br /> 使用已解释的正则表达式。|  
|<xref:System.Threading.Tasks.Task?displayProperty=fullName> 处置|处置对象后，<xref:System.Threading.Tasks.Task?displayProperty=fullName> 方法不再抛出 <xref:System.ObjectDisposedException> 异常（`Task.IAsyncResult.AsyncWaitHandle` 除外）。|此更改支持缓存任务的使用。 例如，方法会返回一个缓存任务来表示已完成的操作，而不是分配新任务。 在以前的 .NET Framework 版本中无法执行此操作，因为任务的任何使用者都可以处置它（呈现为不可用）。|  
|<xref:System.Threading.Tasks.Task?displayProperty=fullName> 操作中未观察到的异常|由于 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 类表示异步操作，因此可捕获在异步处理期间抛出的所有非严重异常。 在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，如果未观察到异常，且代码绝不会等待任务，则异常将不再在终结器线程上传播并在垃圾回收期间不会导致进程崩溃。|此更改增强了使用 <xref:System.Threading.Tasks.Task> 类执行未观察到的异步处理的应用程序的可靠性。 可通过提供 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName> 事件的相应处理程序来还原旧行为。|  
|含超时自变量的 <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=fullName> 方法|在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中，这些方法的行为不一致。 当超时到期时，如果在方法调用之前已完成或取消一个或多个任务，方法会抛出 <xref:System.AggregateException> 异常。 在超时到期时，如果在调用此方法之前尚未完成或取消任何任务，但在调用此方法之后，一个或多个任务进入了这些状态，则该方法返回 `false`。<br /><br /> 在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，如果在超时间隔到期时仍有任务在运行，这些方法重载会返回 `false`；仅当输入任务已取消（无论是在方法调用之前还是之后取消）且没有任务仍在运行时，这些方法重载才会抛出 <xref:System.AggregateException> 异常。|此更改可使方法的行为一致。 不过，应用程序代码可以（但不太可能）依赖已启用超时的 <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=fullName> 重载，以便在至少一个任务在超时到期前就已出错或取消时抛出异常。 在这种情况下，<xref:System.Threading.Tasks.Task.IsCanceled%2A?displayProperty=fullName> 属性可用于同一目的。|  
|支持多定向时的类型转发|利用新的 CodeDOM 功能，编译器可以针对 mscorlib.dll 的目标版本而不是 mscorlib.dll 的 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 版本进行编译。|在 CodeDOM 查找已转发的类型的两个定义时，此更改将阻止编译器警告（以及将警告视为错误的情况下的编译失败）。 仅在单个位置混合不同的引用程序集版本时，此更改才可能产生意外的副作用。|  
|<xref:System.Collections.Generic.List%601.ForEach%2A?displayProperty=fullName>|如果集合元素被修改，枚举器会抛出 <xref:System.InvalidOperationException> 异常。|此更改仅适用于面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序，且应不会产生负面影响。 这将保护数据完整性并更有可能标识争用情况。|  
|<xref:System.Uri?displayProperty=fullName>|对国际资源标识符 (IRI) 分析进行的两项更改会影响面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序中的 URI：<br /><br /> [\<iriParsing>](../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md) 默认启用，无法禁用。 以前，它在默认情况下是禁用的。<br /><br /> 将不再对 URI 的非宿主部分执行 Unicode 范式 C (NFC)。 以前，当启用 `<iriParsing>` 时，会对整个 URI 执行 NFC。|包含非 NFC（范式 C）的规范化文件名称的 URI 将不是规范化的范式 C。 如果 IRI 分析使用非规范化的字符串来访问具有规范化文件名的文件，可能会导致应用程序失败。 这只会影响面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序。|  
|<xref:System.Uri?displayProperty=fullName>|无效的 `mailto:` URL 会在 <xref:System.Uri> 类构造函数中抛出异常。|这只会影响将重新编译且面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序。|  
|<xref:System.Uri?displayProperty=fullName>|在面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序中，将保留原始 URL 字符串（例如，`http://www.proseware.com/LLC./About.aspx`）中路径段末端的尾随点。 （请注意，已移除只包含一个或两个点的路径段（例如 `http://www.proseware.com/..` 或 `http://www.proseware.com/./default.htm`），但保留了含有两个以上连续点的路径段（例如 `http://localhost/dir1/.../dir2`）。|此更改仅影响面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序。 依赖将被移除的尾随点的应用程序可能会失败。|  
|<xref:System.Uri?displayProperty=fullName>|在面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序中，允许 `file://` URI 中的查询；? 字符不转译，因为它解释为路径的一部分。|此更改仅影响面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序。 依赖转译 ?  字符的应用程序可能会失败。|  
|<xref:System.Uri?displayProperty=fullName>|在面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序中，从 U+0080 到 U+009F 的 Unicode 控制字符被错误编码。|通常，URI 中不使用 Unicode 控制字符。|  
|<xref:System.Uri.EscapeDataString%2A?displayProperty=fullName>、<xref:System.Uri.EscapeUriString%2A?displayProperty=fullName> 和 <xref:System.Uri.UnescapeDataString%2A?displayProperty=fullName>|保留字符和非保留字符的列表现在支持 [RFC 3986](http://tools.ietf.org/html/rfc3986)。|具体更改：<br /><br /> <xref:System.Uri.EscapeDataString%2A> 根据 RFC 3986 转义保留字符。<br /><br /> <xref:System.Uri.EscapeUriString%2A> 不转义保留字符。<br /><br /> 如果遇到无效的转义序列，<xref:System.Uri.UnescapeDataString%2A> 不会抛出异常。<br /><br /> 未保留的转义字符已取消转义。|  
|<xref:System.Uri.IsWellFormedUriString%2A?displayProperty=fullName>|自 .NET Framework 4.5 起，根据 [RFC 3986](http://tools.ietf.org/html/rfc3986) 和 [RFC 3987](http://tools.ietf.org/html/rfc3987)，始终认为字符串的格式正确。 在 .NET framework 以前的版本中，仅当已启用 URI 解析和 IDN 解析时，才认为字符格式正确，符合 RFC 3986 和 RFC 3987。|对于面向 .NET Framework 4.5 或更高版本的应用，此方法针对某些面向 NET Framework 早期版本的应用视为格式正确的 URI 返回 `false`。 例如，第一段中含冒号的相对 URI（如“2013.05.29_14:33:41”）不再视为是正确的格式。<br /><br /> 请注意，此更改仅影响面向 .NET Framework 4.5 或更高版本的应用。|  
|<xref:System.Threading.Tasks.TaskFactory.FromAsync%2A?displayProperty=fullName>|<xref:System.Threading.Tasks.TaskFactory.FromAsync%2A?displayProperty=fullName> 现在可以访问 <xref:System.IAsyncResult.CompletedSynchronously%2A?displayProperty=fullName> 属性。 不正确地实现 <xref:System.IAsyncResult.CompletedSynchronously%2A?displayProperty=fullName> 现在可能会导致 <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A?displayProperty=fullName> 方法调用中出现未定义的行为。|如果 <xref:System.IAsyncResult.CompletedSynchronously%2A?displayProperty=fullName> 属性的实现代码错误地返回 `true`，生成的任务将无法完成。|  
  
<a name="sql"></a>   
## <a name="data"></a>数据  
  
### <a name="sqlclient"></a>SQLClient  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|能够从在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 下运行的托管代码连接到 SQL Server 数据库。|已修改现有同步 API 代码路径来添加异步支持。|存在非 IFS Winsock 基本服务提供程序 (BSP) 或分层服务提供程序 (LSP) 可能会影响连接到 SQL Server 的能力。 有关详细信息，请参阅 Microsoft 支持网站上的[安装非 IFS LSP 时，SetFileCompletionNotificationModes API 导致 IO 完成端口无法正常工作](http://go.microsoft.com/fwlink/p/?LinkId=256032) 。|  
|<xref:System.Data.SqlClient.SqlConnection?displayProperty=fullName> 类型|不再支持与 SQL Server 1997 数据库的连接。|在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 下运行的应用程序无法连接到 SQL Server 1997 数据库。|  
|<xref:System.Data.SqlClient.SqlConnection?displayProperty=fullName> 类型|不再支持使用虚拟接口适配器 (VIA) 协议来连接到 SQL Server 数据库。|在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 下运行的应用程序无法使用 VIA 连接到 SQL Server 数据库。|  
|<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> 类型|将数据插入列后，<xref:System.Data.SqlClient.SqlBulkCopy> 使用目标列的编码，而不是 `VARCHAR` 和 `CHAR` 类型的默认编码。|在目标列未使用默认编码时，此更改会消除使用此默认编码所引起的数据损坏的可能性。 在极少数情况下，如果对编码进行的更改导致数据过大而无法适应目标列，现有应用程序可能会抛出 <xref:System.Data.SqlClient.SqlException> 异常。|  
|<xref:System.Data.SqlClient?displayProperty=fullName> 排序规则序列|`sql_variant` 数据使用 `sql_variant` 排序规则而不是数据库排序规则。|如果数据库排序规则与 `sql_variant` 排序规则不同，则此更改将解决可能的数据损坏。 依赖损坏的数据的应用程序可能会失败。|  
  
### <a name="entity-framework"></a>Entity Framework  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|<xref:System.Data.Objects.ObjectContext.CreateDatabase%2A?displayProperty=fullName> 方法创建的日志文件|直接调用 <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A> 方法或通过结合使用 Code First 与 SqlClient 提供程序和连接字符串中的 `AttachDBFilename` 值来调用此方法时，会创建名为 *filename*_log.ldf（而非 *filename*.ldf）的日志文件（其中，*filename* 是 `AttachDBFilename` 值指定的文件名）。|此更改通过提供根据 SQL Server 规范命名的日志文件来改进调试。 它应该不会产生意外的副作用。|  
|数据定义语言 (DDL) API|指定 `AttachDBFilename` 时，DDL API 的行为具有如下所示的更改：<br /><br /> 连接字符串不需要指定 `Initial Catalog` 值。 以前需要 `AttatchDBFilename` 和 `Initial Catalog`。<br /><br /> 如果 `AttatchDBFilename` 和 `Initial Catalog` 均已指定且给定的 MDF 文件已存在，<xref:System.Data.Objects.ObjectContext.DatabaseExists%2A?displayProperty=fullName> 方法会返回 `true`。 以前，它会返回 `false`。<br /><br /> 如果 `AttatchDBFilename` 和 `Initial Catalog` 均已指定且给定的 MDF 文件已存在，调用 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A?displayProperty=fullName> 方法会删除文件。<br /><br /> 如果连接字符串指定了 `AttachDBFilename` 值，但 MDF 和 `Initial Catalog` 不存在，调用 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A?displayProperty=fullName> 方法会抛出 <xref:System.InvalidOperationException> 异常。 以前抛出的是 <xref:System.Data.SqlClient.SqlException> 异常。|利用这些更改，可以更轻松地生成使用 DDL API 的工具和应用程序。 这些更改会影响以下方案中的应用程序兼容性：<br /><br /> 用户直接编写执行 `DROP DATABASE` 命令的代码，而不是在 <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A?displayProperty=fullName> 返回 `true` 时调用 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A?displayProperty=fullName>。 如果未附加数据库但存在 MDF 文件，则会中断现有代码。<br /><br /> 在用户编写的代码中，<xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A?displayProperty=fullName> 方法在 `Initial Catalog` 和 MDF 文件不存在时应抛出 <xref:System.Data.SqlClient.SqlException> 异常，而非 <xref:System.InvalidOperationException> 异常。|  
|<xref:System.Data.Objects.ObjectContext.CreateDatabase%2A?displayProperty=fullName> 和 <xref:System.Data.Common.DbProviderServices.CreateDatabase%2A?displayProperty=fullName> 方法|如果在创建空数据库后无法创建数据库对象，方法会尝试删除创建的数据库，并传播原始异常 <xref:System.Data.SqlClient.SqlException>。 如果无法尝试删除数据库，方法会抛出 <xref:System.InvalidOperationException> 异常。|此更改将阻止创建不可用的空数据库。 由于成功删除数据库现在会传播原始异常 <xref:System.Data.SqlClient.SqlException>，因此异常处理可能会有所变化。|  
|<xref:System.Data.Objects.ObjectContext.Translate%2A?displayProperty=fullName> 和 <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%2A?displayProperty=fullName> 方法|如果 `T` 是枚举类型，则此方法将正确返回数据库中的数据。  以前不支持枚举类型，因此结果总是转换为零或转换为枚举类型。 实体框架不支持的基础类型（如 <xref:System.UInt16>、<xref:System.UInt32> 和 <xref:System.UInt64>）仍返回零或被转换成含基础值零的枚举类型。|枚举支持是 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中 Entity Framework 的新增功能。 但是，如果开发人员代码取决于为零的结果，则会由于特定代码导致应用程序错误。|  
  
### <a name="linq"></a>LINQ  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|<xref:System.Linq.Enumerable.Empty%2A?displayProperty=fullName> 方法|方法返回缓存的内部实例，而不返回新类型 <xref:System.Collections.Generic.IEnumerable%601>。|此更改可增强性能。 不过，依赖通过多次调用 <xref:System.Linq.Enumerable.Empty%2A?displayProperty=fullName> 来获取两个不同的空类型的代码可能会无法运行。|  
  
<a name="network"></a>   
## <a name="networking"></a>网络  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|<xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName> 命名空间的类型和成员|类型和成员在 [!INCLUDE[win8](../../../includes/win8-md.md)] 上不受支持。 尝试调用这些类型和成员会导致 <xref:System.PlatformNotSupportedException> 异常抛出。|应用程序不能再使用 [!INCLUDE[win8](../../../includes/win8-md.md)] 上的这些类型和成员。|  
|<xref:System.Net.Mail.MailMessage> 对象的序列化和反序列化。|在 .NET Framework 4.5 中，电子邮件可以包含非 ASCII 字符。 在 .NET Framework 4 中，仅支持 ASCII 字符。|包含非 ASCII 字符且在 .NET Framework 4.5 控制下序列化的 <xref:System.Net.Mail.MailMessage> 对象无法在 .NET Framework 4 控制下进行反序列化。|  
  
<a name="Printing"></a>   
## <a name="printing"></a>打印  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|<xref:System.Printing.PrintSystemJobInfo.JobStream%2A?displayProperty=fullName>|此属性将公开打印作业的流，并允许用户通过写入该流将原始数据发送到基础操作系统打印组件。<br /><br /> 从 Windows 操作系统的 Windows 8 和更高版本上的 .NET Framework 4.5 开始，写入到此流的数据必须采用作为包流的 XPS 格式。|若要输出打印内容，可以执行下列任一操作：<br /><br /> 使用 <xref:System.Windows.Xps.XpsDocumentWriter> 类输出打印内容。 这是建议的替代项。<br /><br /> 请确保发送到 <xref:System.Printing.PrintSystemJobInfo.JobStream%2A?displayProperty=fullName> 属性返回的流的数据为 XPS 格式的包流。|  
  
<a name="serialize"></a>   
## <a name="serialization"></a>序列化  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|使用 <xref:System.Xml.Serialization.XmlSerializer> 类进行序列化|在 WCF 4.5 中，<xref:System.Xml.Serialization.XmlSerializer> 类优化为撤消了对 C# 编译器的依赖。 此更改为冷启动方案带来了显著的性能提升。|此更改可能在 WCF 4 中编译而针对 WCF 4.5 运行的 XML 序列化代码中引发问题。 如果在 WCF 4.5 中运行现有 XML 序列化代码时遇到任何问题，请使用下面的配置元素还原为 WCF 4 中的 XmlSerializer 行为：<br /><br /> `<configuration>    <system.xml.serialization>    <xmlSerializer useLegacySerializerGeneration="true"/>    </system.xml.serialization> </configuration>`|  
|使用 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> 类进行序列化和反序列化|使用 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 进行的序列化可以编码对象的内部状态，但不能保证跨 .NET Framework 版本的一致性。  存在差异时，在某个版本的 .NET Framework 中进行序列化的内容在其他版本的 .NET Framework 上进行反序列化时可能会失败。|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> 类不能保证跨版本兼容性。 请改用 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> 和 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> 类。|  
  
<a name="tools"></a>   
## <a name="tools-and-resources"></a>工具和资源  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|MSBuild|当你在命令提示符处运行 MSBuild 时，它将遵从禁用特定项目的生成的解决方案配置文件。|在由 Visual Studio 调用和在命令提示符处运行时，MSBuild 的行为是相同的。 不必创建单独的解决方案或移除解决方案中的项目便可在解决方案中生成项目的子集。|  
|MSBuild|MSBuild 项目文件中的 `TreatAsLocalProperty` 属性可防止在全局级重写特定属性，包括 `OutDir` 属性。|如果 `OutDir` 是导入 MS.Common.Targets 文件后被重写的全局属性，则对 `OutDir` 属性的重写可能导致潜在中断。|  
|Windows 错误报告：Watson 存储桶|托管崩溃基于若干条件（其中一个是程序集版本）进行分类。 在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，使用文件版本而不是程序集版本。|由于程序集版本只在主要版本之间更改，因此使用文件版本（而不是程序集版本）作为能使你确定已包含在托管崩溃中的程序集的特定版本的类别。|  
|MSBuild|垃圾回收器不会自动回收 <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName> 集合中的项目数据。|如果将项目显式加载到 <xref:Microsoft.Build.Evaluation.ProjectCollection> 集合中，应为集合的每个成员调用 <xref:Microsoft.Build.Evaluation.ProjectCollection.UnloadProject%28Microsoft.Build.Evaluation.Project%29> 方法。|  
  
<a name="asp"></a>   
## <a name="aspnet"></a>ASP.NET  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|ASP.NET IIS 注册工具 (aspnet_regiis.exe)|在 [!INCLUDE[win8](../../../includes/win8-md.md)] 上，不支持用于安装和卸载 ASP.NET 的 `–i` 和 `–u` 选项。|若要安装或卸载带 IIS 8 的 ASP.NET 4.5，请使用“打开或关闭 Windows 功能”对话框、服务器管理工具或 `dism.exe` 命令行工具。|  
|<xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> 控件|<xref:System.Web.UI.Page.LoadComplete?displayProperty=fullName> 事件不再导致 <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> 控件在创建/更新/删除参数变化时调用数据绑定。|此更改免去了不必要地转到数据库，可防止重置控件值，并能生成与其他数据控件（如 <xref:System.Web.UI.WebControls.SqlDataSource> 和 <xref:System.Web.UI.WebControls.ObjectDataSource>）一致的行为。 在应用程序依赖在 <xref:System.Web.UI.Page.LoadComplete?displayProperty=fullName> 事件中调用数据绑定的极少数情况下，此更改会生成不同的行为。|  
|<xref:System.Net.WebUtility.HtmlDecode%2A?displayProperty=fullName>、<xref:System.Net.WebUtility.UrlDecode%2A?displayProperty=fullName> 和 [System.Web.Helpers.Json.Decode](https://msdn.microsoft.com/library/system.web.helpers.json.decode.aspx) 方法|默认情况下，解码方法不再将无效的输入序列解码为无效的 UTF-16 字符串。 相反，它们将返回原始的输入。|仅当你存储二进制数据而不是字符串中的 UTF-16 数据时，解码器输出中的更改才会起作用。 若要显式控制此行为，请将 [\<appSettings>](http://msdn.microsoft.com/en-us/0d65a3f1-c522-423d-89b6-44921b6daebb) 元素的 `aspnet:AllowRelaxedUnicodeDecoding` 特性设置为 `true` 以启用旧行为，或设置为 `false` 以启用当前行为。|  
|<xref:System.Net.WebUtility.HtmlEncode%2A?displayProperty=fullName> 方法|对于定位 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序，当基本多语言平面 (BMP) 外的字符传递到 <xref:System.Net.WebUtility.HtmlDecode%2A?displayProperty=fullName> 方法时，这些字符可正确往返。|此更改不应对当前应用程序有任何影响。 若要还原原始行为，请将 [\<httpRuntime>](http://msdn.microsoft.com/library/e1f13641\(v=vs.100\).aspx) 元素的 `targetFramework` 特性设置为除“4.5”以外的其他字符串。 还可以设置 `unicodeEncodingConformance` 配置元素的 `unicodeDecodingConformance` 和 `<webUtility>` 特性以单独控制 .NET Framework 的目标版本的行为。|  
|<xref:System.Web.HttpRequest.ContentEncoding%2A?displayProperty=fullName> 属性|禁止 UTF-7 编码。|在某些情况下，取决于传入的 UTF-7 数据的应用程序数据将不会正确解码。 这应该很少见，但可以使用 [\<appSettings>](http://msdn.microsoft.com/en-us/0d65a3f1-c522-423d-89b6-44921b6daebb) 元素的 `aspnet:AllowUtf7RequestContentEncoding` 特性来还原旧行为。|  
|<xref:System.Web.HttpUtility.JavaScriptStringEncode%2A?displayProperty=fullName>|从 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 开始，该方法可转义 (&) 符。|如果应用程序依赖此方法的旧行为，可以在配置文件中的 [ASP.NET appSettings 元素](http://msdn.microsoft.com/en-us/bb60e711-0669-4118-a54d-8dd71e009a00)中添加 `aspnet:JavaScriptDoNotEncodeAmpersand` 设置。|  
|<xref:System.Web.Security.MachineKey.Encode%2A?displayProperty=fullName> 和 <xref:System.Web.Security.MachineKey.Decode%2A?displayProperty=fullName> 方法|这些方法现在已过时。|调用这些方法的代码编译会产生编译器警告。 推荐的替代方法是 <xref:System.Web.Security.MachineKey.Protect%2A?displayProperty=fullName> 和 <xref:System.Web.Security.MachineKey.Unprotect%2A?displayProperty=fullName>。|  
  
<a name="ClickOnce"></a>   
## <a name="clickonce"></a>ClickOnce  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|通过 ClickOnce 使用 SHA-256 代码签名证书发布的应用。|使用 SHA256 对可执行文件签名。 以前，无论代码签名证书是 SHA-1 还是 SHA-256，都使用 SHA1 进行签名。 这适用于：<br /><br /> 使用 Visual Studio 2012 或更高版本生成的所有应用程序。<br /><br /> 使用 Visual Studio 2010 或更早版本在安装了 .NET Framework 4.5 的系统上生成的应用程序。<br /><br /> 此外，如果安装了 .NET Framework 4.5 或更高版本，则 ClickOnce 清单也会采用 SHA-256 签名，因为 SHA-256 证书与编译所采用的 .NET Framework 版本无关。|更改 ClickOnce 可执行文件的签名方式仅影响 Windows Server 2003 系统；它们需要安装 [KB 938397](http://support.microsoft.com/kb/938397)。<br /><br /> 即使应用是面向 .NET Framework 4 或早期版本，对使用 SHA-256 签名的清单进行更改，将引入依赖 .NET Framework 4.5 或更高版本的运行时。 此问题已在 Visual Studio 2013 Update 3 和 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 中解决。 有关 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 解决方案，请参阅[运行时更改](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)。|  
  
<a name="mef"></a>   
## <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|<xref:System.ComponentModel.Composition.Primitives.ComposablePartCatalog?displayProperty=fullName> 及其派生类|自 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 起，MEF 目录实现 <xref:System.Collections.IEnumerable>，因此不能再用于创建序列化程序（<xref:System.Xml.Serialization.XmlSerializer> 对象）。|尝试对 MEF 目录进行序列化会引发异常。|  
  
<a name="web"></a>   
## <a name="web-applications"></a>Web 应用程序  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|承载来自 .NET Framework 1.1 和 2.0 的控件的托管浏览器|Internet Explorer 中阻止对这些控件的承载。|Internet Explorer 将无法启动使用用于承载控件的托管浏览器的应用程序。 通过将注册表子项 HKLM/SOFTWARE/MICROSOFT/.NETFramework 的 EnableIEHosting 值设置为 1（针对 x86 系统和 x64 系统的 32 位进程），并将注册表子项 HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework 的 EnableIEHosting 值设置为 1（针对 x64 系统的 64 位进程），可还原之前的行为。|  
  
<a name="wcf"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
 除了下面的应用程序兼容性问题外，请参阅[序列化](#serialize)部分，了解与序列化相关的问题。  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|超过 `maxRequestLength`（在 ASP.NET 中）或 `maxReceivedMessageSize`（在 WCF 中）的 Internet Information Services (IIS) 或 ASP.NET 开发服务器中所承载的 WCF Web 服务中的消息|HTTP 状态代码已从 400（错误请求）更改为 413（请求实体太大），超过 `maxRequestLength` 或 `maxReceivedMessageSize` 设置的消息抛出 <xref:System.ServiceModel.ProtocolException> 异常。 这包括传输模式为 <xref:System.ServiceModel.TransferMode> 的情况。|在信息长度超过 ASP.NET 或 WCF 所允许的限制的情况下，此更改有利于调试。<br /><br /> 你必须基于 HTTP 400 状态代码修改执行处理的任何代码。|  
|OData URL 中的 `Replace`|默认情况下，禁用 OData URL 中的 `Replace` 方法。|如果禁用 OData `Replace`（现为默认设置），用户请求将引发异常，且请求会失败。|  
|<xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>|如果应用程序代码已添加显式终结点，<xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName> 对象不再添加默认终结点。|如果客户端应用程序尝试连接到默认情况下不再添加的终结点，将发生 HTTP 错误。|  
  
<a name="winForms"></a>   
## <a name="windows-forms"></a>Windows 窗体  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|System.Drawing.dll|程序集的 `CheckForOverflowUnderflow` 属性设置为 `true`。|之前在发生溢出时，结果会在不提示的情况下被截断。 现在会抛出 <xref:System.OverflowException> 异常。|  
|<xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName> 构造函数|此构造函数已弃用。|构造函数不能在 64 位系统上运行。 请改用 <xref:System.Drawing.Imaging.EncoderParameter.%23ctor%28System.Drawing.Imaging.Encoder%2CSystem.Int32%2CSystem.Drawing.Imaging.EncoderParameterValueType%2CSystem.IntPtr%29?displayProperty=fullName> 构造函数。|  
  
<a name="wpf"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 除了下面的应用程序兼容性问题外，请参阅[序列化](#serialize)部分，了解与序列化相关的问题。  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|<xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit%2A?displayProperty=fullName> 属性|<xref:System.Windows.Controls.TextBox> 和 <xref:System.Windows.Controls.RichTextBox> 类的撤消操作数默认上限已从 -1（无限制）更改为 100。|此更改不应有负面影响。 不过，可以在实例化控件后显式设置 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit%2A> 属性。|  
|<xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> 枚举|已向枚举添加 <xref:System.Windows.Controls.PageRangeSelection> 和 <xref:System.Windows.Controls.PageRangeSelection> 成员。|此更改不应对现有应用程序有任何影响。 对于使用此枚举的现有成员，默认为 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>。|  
|<xref:System.Windows.DataTemplate> 元素|<xref:System.Windows.DataTemplate> 元素现在显示在 UI 自动化 (UIA) 树的控件视图中。|此更改将提高可访问性。 但是，它会影响依赖之前的 UIA 树结构来定位相邻元素的测试工具。|  
|同步 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> 属性及其绑定到的属性|在某些情况下，如果在数据绑定写入操作期间 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName> 属性被修改，此属性会反映已绑定数据的属性值的旧值。|这不应有负面影响。 不过，可以通过将 <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty%2A?displayProperty=fullName> 属性设置为 `false` 来还原旧行为。|  
|<xref:System.Windows.Controls.TextBox?displayProperty=fullName> 属性|当 <xref:System.Windows.Controls.TextBox?displayProperty=fullName> 控件处于非活动状态时，框中选定文本的显示颜色与文本框处于活动状态时的颜色不同。|可以通过将 <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported%2A?displayProperty=fullName> 属性设置为 `false` 来还原旧行为。|  
|<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName>|如果从 <xref:System.Windows.Controls.Primitives.MultiSelector.CanSelectMultipleItems%2A> 设置为 `true` 的 <xref:System.Windows.Controls.Primitives.MultiSelector> 派生的控件在其 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 集合中有重复项，重复项会多次出现。 将这些项从数据源中删除（例如，通过调用 `Items.Clear`）无法将其从 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 集合中删除；只能删除第一个实例。<br /><br /> 后续使用 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 集合（如通过调用 `SelectedItems.Clear`）可能会遇到问题（如 <xref:System.ArgumentException> 抛出），因为 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 集合包含数据源中不再存在的项。|此问题已在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 中得到解决。 如果 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 集合有重复项，你将这些重复项从数据源中删除，并希望继续使用 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A?displayProperty=fullName> 集合，请升级到 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]。|  
|<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy%2A?displayProperty=fullName>|在 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 中，该方法返回对当前实例的引用。 在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，它会返回新的实例。|假定相等引用的代码指示将立即正确执行在正确的上下文中执行的线程。 不过，鉴于有此更改，应对调用 <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy%2A?displayProperty=fullName> 的代码进行测试。|  
|使用通过调用 <xref:System.Windows.Interop.HwndSource.AddHook%2A?displayProperty=fullName> 方法添加的处理程序监视 `WM_POWERBROADCAST` 消息。|窗口必须通过将其句柄传递到 [RegisterPowerSettingNotification](https://msdn.microsoft.com/library/windows/desktop/aa373196.aspx) 函数，从而显式注册 `WM_POWERBROADCAST` 通知。 通过 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]，WPF 会自动为所有窗口执行此操作。 从 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 开始，WPF 将自动注册一个特殊窗口，但不会自动注册大多数应用窗口。|处理 `WM_POWERBROADCAST` 通知的代码不会执行。<br /><br /> 若要继续接收 `WM_POWERBROADCAST` 通知，请调用 [RegisterPowerSettingNotification](https://msdn.microsoft.com/library/windows/desktop/aa373196.aspx) 函数，以便为 WPF 窗口（通常为主应用程序窗口）注册 `WM_POWERBROADCAST` 通知。 在使用 C# 开发的 WPF 应用程序中，还必须选中项目属性“生成”选项卡上的“允许不安全代码”框。<br /><br /> 此外，如果要注册通知的窗口在应用程序关闭前无法一直存在，应调用 [UnregisterPowerSettingNotification](https://msdn.microsoft.com/library/windows/desktop/aa373237.aspx) 函数，并向其传递通过调用 [RegisterPowerSettingNotification](https://msdn.microsoft.com/library/windows/desktop/aa373196.aspx) 函数返回的 `HPOWERNOTIFY` 句柄，从而取消注册。|  
  
<a name="wwf"></a>   
## <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|System.Activities.dll 安全性|程序集是使用 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 特性进行标记。|派生类不能使用 <xref:System.Security.SecurityCriticalAttribute> 进行标记。 以前，必须使用 <xref:System.Security.SecurityCriticalAttribute> 标记派生类型。 但是，此更改不应有实际影响。|  
|WF 3.0 类型和成员|WF 3.0 的类型和成员现在已标记为过时。|尝试编译使用 WF 3.0 类型或成员的源代码会生成一个编译器错误。 应使用 <xref:System.Activities> 命名空间中的 WF 4 类型和成员。|  
|<xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> 类|<xref:System.Activities.Presentation.DragDropHelper> 类包括支持对多个对象进行拖放操作的新方法。 支持拖动单个对象的现有拖放方法已过时。 （有关详细信息，请参阅[类库中过时的内容](../../../docs/framework/whats-new/whats-obsolete.md)。）|虽然旧方法已被弃用，但编译器和公共语言运行时将继续支持这些方法。 但是，新方法将提供更强大的功能。 某些现有方法的建议替换方法如下：<br /><br /> 使用 <xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName> 来替代 <xref:System.Activities.Presentation.DragDropHelper.DoDragMove%28System.Activities.Presentation.WorkflowViewElement%2CSystem.Windows.Point%29?displayProperty=fullName>。<br /><br /> 使用 <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Activities.Presentation.WorkflowViewElement%29> 来替代 <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView%28System.Windows.DragEventArgs%29>。<br /><br /> 使用 <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItems%28System.Windows.DragEventArgs%29> 来替代 <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem%28System.Windows.DragEventArgs%29>。<br /><br /> 使用 <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObjects%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29> 来替代 <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject%28System.Windows.DependencyObject%2CSystem.Windows.DragEventArgs%2CSystem.Activities.Presentation.EditingContext%29>。|  
|<xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 方法调用的重载解析|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 新增了包括 <xref:System.Action?displayProperty=fullName> 类型参数的重载。 重新编译现有代码时，编译器可能会将含有 <xref:System.Delegate> 参数的 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 方法调用解析为含有 <xref:System.Action?displayProperty=fullName> 参数的 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 方法调用。|如果含有 <xref:System.Delegate> 参数的 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 重载调用被解析为含有 <xref:System.Action?displayProperty=fullName> 参数的 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 重载调用，可能会出现以下行为差异：<br /><br /> 如果有异常抛出，则无法触发 <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter?displayProperty=fullName> 和 <xref:System.Windows.Threading.Dispatcher.UnhandledException?displayProperty=fullName> 事件。 相反，异常由 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 事件处理。<br /><br /> 在操作完成前，将无法调用一些成员（如 <xref:System.Windows.Threading.DispatcherOperation.Result%2A?displayProperty=fullName>）。|  
|<xref:System.Activities.Expressions.Literal%601?displayProperty=fullName> 类|关联的 <xref:System.Windows.Markup.ValueSerializer> 对象将 `Second` 和 `Millisecond` 组件不为零且（对于 <xref:System.DateTime> 值）<xref:System.DateTime.Kind%2A?displayProperty=fullName> 属性不是 <xref:System.DateTimeKind> 的 <xref:System.DateTime> 或 <xref:System.DateTimeOffset> 对象转换成属性元素语法，而不是字符串。|此更改允许 <xref:System.DateTime> 和 <xref:System.DateTimeOffset> 值往返。 假定输入 XAML 是采用特性语法的自定义 XAML 分析器将无法正常运行。|  
  
<a name="xml"></a>   
## <a name="xml-xslt"></a>XML、XSLT  
  
|功能|更改|影响|  
|-------------|------------|------------|  
|`XDocument.Validate` 方法|如果将 <xref:System.Xml.Linq.LoadOptions?displayProperty=fullName> 值传递给 <xref:System.Xml.Linq.XDocument.Load%2A> 方法并出现验证错误，<xref:System.Xml.Schema.XmlSchemaException.LineNumber%2A?displayProperty=fullName> 和 <xref:System.Xml.Schema.XmlSchemaException.LinePosition%2A?displayProperty=fullName> 属性现在包含行信息。|依赖 <xref:System.Xml.Schema.XmlSchemaException.LineNumber%2A?displayProperty=fullName> 和 <xref:System.Xml.Schema.XmlSchemaException.LinePosition%2A?displayProperty=fullName> 属性值的异常处理代码将无法再发挥作用。|  
|使用 <xref:System.Xml.XmlTextReader?displayProperty=fullName> 加载 XML 文件|DTD 实体扩展限制为 10,000,000 个字符。|加载不带 DTD 实体扩展或带有限的 DTD 实体扩展的 XML 文件不受影响。 包含了扩展到 10,000,000 个字符以上的 DTD 实体的文件将无法加载，且会立即引发异常。|  
|<xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=fullName> 类的向前兼容性模式|在 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 中，XSLT 1.0 向前兼容性具有以下问题：<br /><br /> 如果其版本设置为 2.0，并且分析器遇到无法识别的 XSLT 1.0 构造，则无法加载样式表。<br /><br /> 如果将样式表版本设置为 1.1，则 `xsl:sort` 构造无法对数据进行排序。<br /><br /> 在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，这些问题已修复，并且 XSLT 1.0 向前兼容性模式可正常工作。|XSLT 1.0 向前兼容性模式现在可以像以前那样工作。|  
|XSLT 文件过于复杂时显示的异常消息|在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，XSLT 文件过于复杂时显示的错误消息的文本为“样式表太复杂”。 在早期版本中，错误消息为“XSLT 编译错误”。|取决于错误消息的文本的应用程序代码将不再有效。 但是，异常类型保持不变，因此，此更改不会造成实际影响。|  
|xsd:anyURI 的 XML 构架验证|在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，XML 架构验证更为严格。 如果使用 xsd:anyURI 来验证 URL（如 mailto 协议），则当 URL 中有空格时，验证将失败。 在 .NET Framework 的早期版本中，验证将成功。|此更改仅影响面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的应用程序。|  
  
## <a name="see-also"></a>另请参阅  
 [类库中过时的内容](../../../docs/framework/whats-new/whats-obsolete.md)   
 [新增功能](../../../docs/framework/whats-new/index.md)   
 [应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility.md)   
 [4.5.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [4.5.2 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
