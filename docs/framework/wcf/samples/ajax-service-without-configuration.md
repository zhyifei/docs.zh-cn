---
title: 无配置的 AJAX 服务
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 9e3ddd451bffc4135f236164a74fe68a63a243a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ajax-service-without-configuration"></a>无配置的 AJAX 服务
此示例演示如何使用 Windows Communication Foundation (WCF) 来创建基本的 ASP.NET 异步 JavaScript 和 XML (AJAX) 服务 （你可以通过从 Web 浏览器客户端使用 JavaScript 代码访问的服务） 而不使用任何配置设置。 该服务在 .svc 文件中使用特殊语法来自动启用 AJAX 终结点。  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 对 AJAX 的支持经过了优化，以便通过 `ScriptManager` 控件与 ASP.NET AJAX 一起使用。 有关使用示例[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]与 ASP.NET AJAX，请参阅[Ajax 示例](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)。  
  
> [!NOTE]
>  本主题的最后介绍了此示例的设置过程和生成说明。  
  
 此示例是基于使用 HTTP POST 的 AJAX 服务生成的。 中所述[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例中，<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>用于承载服务。  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 自动将 <xref:System.ServiceModel.Description.WebScriptEndpoint> 添加到服务。 如果不需要对终结点进行任何配置更改，则可从服务的 Web.config 文件中完全移除 `<system.ServiceModel>` 部分。 Web.config 文件包含一些由 ConfigFreeClientPage.aspx 使用的 ASP.NET 设置。 如果不是这样，则可以移除整个 Web.config 文件。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  确保执行中的设置说明[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  生成解决方案 ConfigFreeAjaxService.sln 中所述[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。  
  
3.  导航到http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx（不要打开 ConfigFreeClientPage.aspx 浏览器中从项目目录中）。  
  
> [!NOTE]
>  运行此示例时，请确保不要对 IIS 中的 ServiceModelSamples 文件夹同时启用匿名身份验证和 Windows 身份验证。 如果同时启用了这两种身份验证，请禁用 Windows 身份验证。 运行了该示例后，请启用 Windows 身份验证并运行“iisreset”。  
  
## <a name="see-also"></a>请参阅  
 [基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
