---
title: ".NET Framework 4.5.2 中的重定目标更改 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2be2a828-9052-4738-a965-d4a836cc6384
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# .NET Framework 4.5.2 中的重定目标更改
在极少数情况下，重定目标更改可能影响那些编译为面向 .NET Framework 4.5.2 的应用。 除非在以下表格中另行指定，否则这些更改不会影响面向以前版本的 .NET Framework 但在版本 4.5.2 下运行的二进制文件。 NET Framework 4.5.2 在以下方面包含重定目标更改：  
  
-   [Entity Framework](#EF)  
  
-   [Windows 窗体](#WinForms)  
  
<a name="EF"></a>   
## Entity Framework 重定目标更改  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|使用未分类的限制操作时查询更简单|生成 `JOIN` 语句并包含对限制操作的调用（无需先使用 <xref:System.Data.Objects.ObjectQuery%601.OrderBy%2A>）的查询现在可以生成更简单的 SQL。 升级到 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 后，这些查询生成了比以前版本更复杂的 SQL。|在默认情况下，禁用此功能。 如果 Entity Framework 生成可导致性能降低的额外 `JOIN` 语句，则可以通过将以下项添加到应用程序配置 \(app.config\) 文件的 `<appSettings>` 部分来启用此功能：<br /><br /> `<add key="EntityFramework_SimplifyLimitOperations" value="true" />`|次要|  
  
<a name="WinForms"></a>   
## Windows 窗体重定目标更改  
  
|功能|更改|影响|范围|  
|--------|--------|--------|--------|  
|使用 <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> 方法从剪贴板检索 HTML 格式的数据|对于面向 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 或者在 .NET Framework 4.5.1 或更早版本上运行的应用，<xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> 将 HTML 格式的数据检索为 ASCII 字符串。 因此，非 ASCII 字符（ASCII 代码大于 0x7F 的字符）由两个随机字符表示。 例如，é \(0xE9\) 由 Ã© \(0xC3 0xA9\) 表示。<br /><br /> 对于面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 更高版本且在 .NET Framework 4.5.2 上运行的应用，<xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> 将 HTML 格式的数据检索为 UTF\-8，它可正确代表大于 0x7F 的字符。|如果你使用 HTML 格式的字符串实现了一个编码问题的解决方法（例如，通过将其传递到 <xref:System.Text.UTF8Encoding.GetString%2A?displayProperty=fullName> 方法来显示编码从剪贴板检索的 HTML 字符串），而且你要将应用的目标从版本 4 重定为 4.5，则应该删除该解决方法。|次要|  
  
## 请参阅  
 [运行时更改](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-2.md)   
 [4.5 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)