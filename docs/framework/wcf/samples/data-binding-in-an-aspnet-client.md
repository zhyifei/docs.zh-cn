---
title: "ASP.NET 客户端中的数据绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f7a3c4adb1a72a31029da7f73778a5ed407b2f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="data-binding-in-an-aspnet-client"></a>ASP.NET 客户端中的数据绑定
本示例演示如何在 Web 窗体应用程序中绑定由典型 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务返回的数据。  
  
> [!NOTE]
>  本主题的最后介绍了此示例的设置过程和生成说明。  
  
 本示例演示一个服务，该服务可实现定义“请求-答复”通信模式的协定。 本示例由可从浏览器访问的客户端 Web 窗体应用程序和由 Internet 信息服务 (IIS) 承载的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务组成。  
  
 该服务实现定义“请求-答复”通信模式的协定。 协定由 `IWeatherService` 接口定义，该接口公开一个名为 `GetWeatherData` 的操作。 此操作接受一个城市数组并返回一个 `WeatherData` 对象数组，这些对象表示城市的预报高温和预报低温。  
  
 在 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 客户端 .aspx 页面中，定义了 DataGrid Web 控件，它包含服务返回的数据的图形化表示形式。 .aspx 页面中的代码调用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务获取天气数据并将数据返回到 `WeatherData` 对象数组。 DataGrid 通过将它的 `DataSource` 属性设置为该数组来指定从何处获取数据。 数据绑定通过调用 DataGrid 的 `DataBind` 方法发生。 此代码全部包含在。`aspx` 页面的`Page_Load`方法，因此每次用户刷新浏览器页面时，数据更新数据网格中。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3.  本示例的客户端是运行在开发 Web 服务器下的网站。 若要启动开发 Web 服务器，在命令提示符下键入以下内容:"`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`。 然后浏览到 http://localhost:8000/client。 若要跨计算机运行此示例，请在客户端的 Web.config 文件中将所有对 `localhost` 的引用替换为服务器的计算机名称。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## <a name="see-also"></a>请参阅
