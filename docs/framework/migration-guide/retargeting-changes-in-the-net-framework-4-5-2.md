---
title: ".NET Framework 4.5.2 中的重定目标更改 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2be2a828-9052-4738-a965-d4a836cc6384
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 10af942724ce0207bc6e64f1ebabfdcd2d3488bd
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-452"></a>.NET Framework 4.5.2 中的重定目标更改
在极少数情况下，重定目标更改可能影响那些编译为面向 .NET Framework 4.5.2 的应用。 除非在以下表格中另行指定，否则这些更改不会影响面向以前版本的 .NET Framework 但在版本 4.5.2 下运行的二进制文件。 NET Framework 4.5.2 在以下方面包含重定目标更改：  
  
-   [Entity Framework](#EF)  
  
-   [Windows 窗体](#WinForms)  
  
<a name="EF"></a>   
## <a name="entity-framework-retargeting-changes"></a>实体框架重定目标更改  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|使用未分类的限制操作时查询更简单|生成 `JOIN` 语句并包含对限制操作的调用（无需先使用 <xref:System.Data.Objects.ObjectQuery%601.OrderBy%2A>）的查询现在可以生成更简单的 SQL。 升级到 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 后，这些查询生成了比以前版本更复杂的 SQL。|在默认情况下，禁用此功能。 如果 Entity Framework 生成可导致性能降低的额外 `JOIN` 语句，则可以通过将以下项添加到应用程序配置 (app.config) 文件的 `<appSettings>` 部分来启用此功能：<br /><br /> `<add key="EntityFramework_SimplifyLimitOperations" value="true" />`|次要|  
  
<a name="WinForms"></a>   
## <a name="windows-forms-retargeting-changes"></a>Windows 窗体重定目标更改  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|使用 <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> 方法从剪贴板中检索 HTML 格式数据|对于定位 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 或在 .NET Framework 4.5.1 或更低版本上运行的应用程序，<xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> 以 ASCII 字符串的形式检索 HTML 格式数据。 因此，非 ASCII 字符（ASCII 代码大于 0x7F 的字符）由两个随机字符表示。 例如，é (0xE9) 由 Ã© (0xC3 0xA9) 表示。<br /><br /> 对于定位 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 或更高版本且在 .NET Framework 4.5.2 上运行的应用程序，<xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> 以 UTF-8 的形式（可正确表示大于 0x7F 的字符）检索 HTML 格式数据。|如果实现了解决方法来解决 HTML 格式字符串编码问题（例如，通过将从剪贴板中检索的 HTML 字符串传递到 <xref:System.Text.UTF8Encoding.GetString%2A?displayProperty=fullName> 方法来进行显式编码），而且要将应用程序的目标从版本 4 重定为版本 4.5，应删除此解决方法。|次要|  
  
## <a name="see-also"></a>另请参阅  
 [运行时更改](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-2.md)   
 [4.5 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)
