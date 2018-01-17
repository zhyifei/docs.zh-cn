---
title: "创建数据服务"
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
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57e305fd8b03e8d46c1fdcb7dd551f32062a1009
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-data-service"></a>创建数据服务
在此任务中，你将创建使用示例数据服务[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]公开[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]基于 Northwind 示例数据库的源。 此任务涉及以下几个基本步骤：  
  
1.  创建一个 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web 应用程序。  
  
2.  使用[!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]工具定义数据模型。  
  
3.  向 Web 应用程序添加数据服务。  
  
4.  启用对数据服务的访问。  
  
> [!NOTE]
>  在完成此任务时创建的 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序将在 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 提供的 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Development Server 上运行。 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server 仅支持来自本地计算机的访问。 为了便于在开发的过程中测试数据服务和解决问题，可考虑通过使用 Internet Information Services (IIS) 运行承载数据服务的应用程序。 有关详细信息，请参阅 [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)。  
  
### <a name="to-create-the-aspnet-web-application"></a>创建 ASP.NET Web 应用程序  
  
1.  在[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]上**文件**菜单上，选择**新建**，然后选择**项目**。  
  
2.  在**新项目**对话框中下,[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]或[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]选择**Web**模板，，然后选择**ASP.NET Web 应用程序**。  
  
    > [!NOTE]
    >  如果使用的是 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer，则必须创建新的网站，而不是创建新的 Web 应用程序。  
  
3.  类型`NorthwindService`作为项目的名称。  
  
4.  单击 **“确定”**。  
  
5.  （可选）为 Web 应用程序指定一个特定的端口号。 注意：在快速入门的其余部分使用端口号 `12345`。  
  
    1.  在**解决方案资源管理器**，右键单击的名称[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]项目你刚创建的，然后单击**属性**。  
  
    2.  选择**Web**选项卡，并设置的值**特定端口**向文本框`12345`。  
  
### <a name="to-define-the-data-model"></a>定义数据模型  
  
1.  在**解决方案资源管理器**，右键单击的名称[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]项目，，然后单击**添加新项。**  
  
2.  在**添加新项**对话框中，单击**数据**模板，然后选择**ADO.NET 实体数据模型**。  
  
3.  对于数据模型的名称，键入`Northwind.edmx`。  
  
4.  在[!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]向导中，选择**从数据库生成**，然后单击**下一步**。  
  
5.  通过执行以下步骤中，连接到数据库的数据模型，然后单击**下一步**:  
  
    -   如果你没有已配置的数据库连接，请单击**新连接**并创建新连接。 有关详细信息，请参阅[如何： 创建到 SQL Server 数据库的连接](http://go.microsoft.com/fwlink/?LinkId=123631)。 此 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 实例必须附加了 Northwind 示例数据库。  
  
         \- 或 -  
  
    -   如果已配置一个连接到 Northwind 数据库的数据库连接，请从连接列表中选择该连接。  
  
6.  在向导的最后一页中，选中数据库中所有表对应的复选框，并清除视图和存储过程对应的复选框。  
  
7.  单击**完成**关闭向导。  
  
    > [!NOTE]
    >  此生成的数据模型将在实体类型上公开外键属性。 使用 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 创建的数据模型不包括这些外键属性。 因此，在尝试访问使用 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 创建的 Northwind 数据服务之前，必须更新已创建的所有客户端应用程序的客户端数据服务类，然后才能访问这一版本的 Northwind 数据服务。  
  
### <a name="to-create-the-data-service"></a>创建数据服务  
  
1.  在**解决方案资源管理器**，右键单击的名称你[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]项目，，然后单击**添加新项**。  
  
2.  在**添加新项**对话框中，选择**WCF 数据服务**。  
  
3.  有关服务的名称，键入`Northwind`。  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 将为新服务创建 XML 标记和代码文件。 默认情况下，代码编辑器窗口将打开。 在**解决方案资源管理器**，服务将具有名称为 Northwind 扩展名。 svc.cs 或。 svc.vb。  
  
4.  在数据服务的代码中，用数据模型的实体容器的类型（在此示例中为 `/* TODO: put your data source class name here */`）替换定义数据服务的类定义中的注释 `NorthwindEntities`。 该类定义应如下所示：  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a>启用对数据服务资源的访问  
  
1.  在数据服务的代码中，用下列代码替换 `InitializeService` 函数中的占位符代码：  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     这使得授权客户端能够对指定实体集的资源进行读写访问。  
  
    > [!NOTE]
    >  任何可以访问该 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序的客户端也能够访问由数据服务公开的资源。 在生产数据服务中，为防止对资源进行未经授权的访问，还应保护应用程序本身的安全。 有关更多信息，请参见 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)。  
  
## <a name="next-steps"></a>后续步骤  
 您已成功创建新的数据服务公开[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]必须启用到客户端上具有权限的数据源的访问，基于 Northwind 示例数据库，并且你的源[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web 应用程序。 接下来，将开始从数据服务[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]和将访问[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]源通过 Web 浏览器提交 HTTP GET 请求：  
  
 [从 Web 浏览器访问服务](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a>请参阅  
 [ADO.NET 实体数据模型工具](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
