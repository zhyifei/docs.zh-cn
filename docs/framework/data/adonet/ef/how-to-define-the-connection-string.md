---
title: 如何：定义连接字符串
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: e5b675a50f883825cce97275048447b79b64cc97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150566"
---
# <a name="how-to-define-the-connection-string"></a>如何：定义连接字符串

本主题介绍如何定义在连接到概念模型时使用的连接字符串。 本主题基于[AdventureWorks 销售](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100))概念模型。 AdventureWorks 销售模型用于实体框架文档中与任务相关的主题。 本主题假定您已配置实体框架并定义了 AdventureWorks 销售模型。 有关详细信息，请参阅[如何：手动定义模型和映射文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))。 本主题中的过程也包含在["如何：手动配置实体框架项目](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))"中。

> [!NOTE]
> 如果在 Visual Studio 项目中使用实体数据模型向导，它会自动生成 .edmx 文件并将项目配置为使用实体框架。 有关详细信息，请参阅[：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))。

## <a name="to-define-the-entity-framework-connection-string"></a>定义实体框架连接字符串

- 打开项目的应用程序配置文件 (app.config) 并添加以下连接字符串：

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

如果项目没有应用程序配置文件，则可以通过从 **"项目**"菜单中选择 **"添加新项目**"、选择 **"常规**类别"、"选择**应用程序配置文件**"以及单击"**添加**"来添加一个配置文件。

## <a name="see-also"></a>另请参阅

- [快速入门](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [如何：创建新的 .edmx 文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [ADO.NET 实体数据模型工具](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
