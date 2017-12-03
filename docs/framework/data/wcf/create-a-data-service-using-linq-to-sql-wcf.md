---
title: "如何：使用 LINQ to SQL 数据源创建数据服务（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52529689242342afa8920a7b01b532a24337f562
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>如何：使用 LINQ to SQL 数据源创建数据服务（WCF 数据服务）
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 将实体数据作为数据服务公开。 反射提供程序允许你定义的数据模型，基于任何公开的成员的类，可返回<xref:System.Linq.IQueryable%601>实现。 为了能够更新数据源中的数据，这些类还必须实现 <xref:System.Data.Services.IUpdatable> 接口。 有关详细信息，请参阅[数据服务提供程序](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)。 本主题演示如何创建通过使用反射提供程序来访问 Northwind 示例数据库的 LINQ to SQL 类，以及如何创建基于这些数据类的数据服务。  
  
### <a name="to-add-linq-to-sql-classes-to-a-project"></a>向项目中添加 LINQ to SQL 类  
  
1.  从在 Visual Basic 或 C# 应用程序中，在**项目**菜单上，单击**添加新项**。  
  
2.  单击**LINQ to SQL 类**模板。  
  
3.  名称更改为**Northwind.dbml**。  
  
4.  单击 **“添加”**。  
  
     此时，Northwind.dbml 文件将随即添加到项目中且对象关系设计器（O/R 设计器）将打开。  
  
5.  在**服务器**/**数据库资源管理器**，在 Northwind 下展开**表**并将其拖`Customers`表拖放到对象关系设计器 (O/R设计器）。  
  
     此时将随即创建一个 `Customer` 实体类并显示在设计图面上。  
  
6.  对 `Orders`、`Order_Details` 和 `Products` 表重复步骤 6。  
  
7.  右击表示该 LINQ to SQL 类，然后单击新.dbml 文件**查看代码**。  
  
     这将创建一个名为 Northwind.cs 的新代码隐藏页，其中包含从 <xref:System.Data.Linq.DataContext> 类（在此示例中为 `NorthwindDataContext`）继承的类的分部类定义。  
  
8.  用下列代码替换 Northwind.cs 代码文件的内容。 此代码通过扩展 <xref:System.Data.Linq.DataContext> 以及 LINQ to SQL 生成的数据类来实现反射提供程序：  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>使用基于 LINQ to SQL 的数据模型创建数据服务  
  
1.  在**解决方案资源管理器**，右键单击 ASP.NET 项目中的名称，然后单击**添加新项**。  
  
2.  在**添加新项**对话框中，选择**WCF 数据服务**。  
  
3.  为该服务，提供一个名称，然后单击**确定**。  
  
     Visual Studio 将为新服务创建 XML 标记和代码文件。 默认情况下，代码编辑器窗口将打开。  
  
4.  在数据服务的代码中，用数据模型的实体容器的类型（在此示例中为 `/* TODO: put your data source class name here */`）替换定义数据服务的类定义中的注释 `NorthwindDataContext`。  
  
5.  在数据服务的代码中，用下列代码替换 `InitializeService` 函数中的占位符代码：  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     这使得授权客户端能够访问指定的三个实体集的资源。  
  
6.  若要通过使用 Web 浏览器测试 Northwind.svc 数据服务，请按照本主题中的说明[从 Web 浏览器访问服务](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)。  
  
## <a name="see-also"></a>另请参阅  
 [如何： 创建数据服务使用 ADO.NET 实体框架数据源](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)  
 [如何： 创建数据服务使用反射提供程序](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [数据服务提供程序](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
