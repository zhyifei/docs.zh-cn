---
title: "如何：从工作流应用程序访问服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ffac399e3f7cb3f860128b072251131ac356a2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-a-service-from-a-workflow-application"></a>如何：从工作流应用程序访问服务
本主题说明如何从工作流控制台应用程序调用工作流服务。 它依赖于完成[如何： 使用消息传递活动创建工作流服务](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)主题。 尽管本主题说明如何从工作流应用程序调用工作流服务，但是，当从工作流应用程序调用任何 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务时，同样可以使用相同方法。  
  
### <a name="create-a-workflow-console-application-project"></a>创建工作流控制台应用程序项目  
  
1.  启动 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
2.  负载中创建的 MyWFService 项目[如何： 使用消息传递活动创建工作流服务](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)主题。  
  
3.  右键单击**MyWFService**中的解决方案**解决方案资源管理器**和选择**添加**，**新项目**。 选择**工作流**中**已安装的模板**和**工作流控制台应用程序**从项目类型列表。 将项目命名为 MyWFClient 并保存在默认位置，如以下插图所示。  
  
     ![添加新项目对话框](../../../../docs/framework/wcf/feature-details/media/addnewprojectdlg.JPG "AddNewProjectDlg")  
  
     单击**确定**按钮以关闭**添加新项目对话框**。  
  
4.  创建项目以后，将在设计器中打开 Workflow1.xaml 文件。 单击**工具箱**选项卡以打开工具箱中，如果不是已打开，然后单击图钉保持工具箱窗口打开。  
  
5.  按 Ctrl+F5 生成并启动服务。 与以前一样，将启动 ASP.NET Development Server，并且 Internet Explorer 将显示 WCF 帮助页。 请注意该页面的 URI，因为在下一步中，您必须使用它。  
  
     ![IE 显示 WCF 帮助页和 URI](../../../../docs/framework/wcf/feature-details/media/iewcfhelppagewuri.JPG "IEWCFHelpPageWURI")  
  
6.  右键单击**MyWFClient**项目中**解决方案资源管理器**和选择**添加服务引用**。 单击**发现**按钮以搜索任何服务的当前解决方案。 在“服务”列表中，单击 Service1.xamlx 旁边的三角形。 单击 Service1 旁边的三角形列出由 Service1 服务实现的约定。 展开**Service1**中的节点**服务**列表。 Echo 操作显示在**操作**列表下图中所示。  
  
     ![添加服务引用对话框](../../../../docs/framework/wcf/feature-details/media/addservicereference.JPG "AddServiceReference")  
  
     保留默认命名空间，然后单击**确定**关闭**添加服务引用**对话框。 将显示以下对话框。  
  
     ![添加服务引用通知对话框](../../../../docs/framework/wcf/feature-details/media/asrdlg.JPG "ASRDlg")  
  
     单击**确定**关闭对话框。 接下来，按 Ctrl+Shift+B 生成解决方案。 请注意，在工具箱中添加一个新节调用**MyWFClient.ServiceReference1.Activities**。 展开此部分，请注意，此时已添加“Echo”活动，如以下插图所示。  
  
     ![回显工具箱中的活动](../../../../docs/framework/wcf/feature-details/media/echoactivity.JPG "EchoActivity")  
  
7.  拖放式<!--zz <xref:System.ServiceModel.Activities.Sequence>-->`System.ServiceModel.Activities.Sequence`活动拖放到设计器图面。 它位于**控制流**工具箱的部分。  
  
8.  与<!--zz <xref:System.ServiceModel.Activities.Sequence>-->`System.ServiceModel.Activities.Sequence`活动焦点，请单击**变量**链接，然后添加一个名为的字符串变量`inString`。 为该变量赋予默认值为`"Hello, world"`以及一个名为的字符串变量`outString`下图中所示。  
  
     ![添加变量](../../../../docs/framework/wcf/feature-details/media/instringvar.JPG "inStringVar")  
  
9. 拖放式**Echo**活动放置<!--zz <xref:System.ServiceModel.Activities.Sequence>--> `System.ServiceModel.Activities.Sequence`。 在属性窗口中将绑定`inMsg`参数`inString`变量和`outMsg`参数`outString`变量，如以下插图中所示。 这样会将 `inString` 变量的值传入操作中，然后获取返回值，并将返回值放到 `outString` 变量中。  
  
     ![自变量绑定到变量](../../../../docs/framework/wcf/feature-details/media/argumentbind.JPG "ArgumentBind")  
  
10. 拖放式**WriteLine**活动下面**Echo**活动以显示服务调用所返回的字符串。 **WriteLine**活动位于**基元**工具箱中的节点。 将绑定**文本**参数**WriteLine**活动`outString`变量通过键入`outString`上的文本框中**WriteLine**活动。 现在，此工作流应该如以下插图所示。  
  
     ![完整的客户端工作流](../../../../docs/framework/wcf/feature-details/media/completeclientwf.JPG "CompleteClientWF")  
  
11. 右击 MyWFService 解决方案并选择**设置启动项目...**.选择**多启动项目**单选按钮，然后选择**启动**中每个项目**操作**列下图中所示。  
  
     ![启动项目选项](../../../../docs/framework/wcf/feature-details/media/startupprojects.JPG "StartupProjects")  
  
12. 按 Ctrl+F5 启动服务和客户端。 ASP.NET Development Server 承载服务，Internet Explorer 显示 WCF 帮助页中，和客户端工作流应用程序将在控制台窗口中启动并显示从服务 （"Hello，world"） 返回的字符串。  
  
## <a name="see-also"></a>请参阅  
 [工作流服务](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [如何：使用消息传递活动创建工作流服务](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 [使用工作流中的 Web 项目的 WCF 服务](http://go.microsoft.com/fwlink/?LinkId=207725)
