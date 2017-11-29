---
title: "配置 Windows 进程激活服务以用于 Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 49a6e009b763ad75143e9ad301b257ec148b5839
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a>配置 Windows 进程激活服务以用于 Windows Communication Foundation
本主题介绍在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中设置 Windows 进程激活服务（也称为 WAS）使其承载不通过 HTTP 网络协议进行通信的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务所需的步骤。 下面的部分略述此配置的步骤：  
  
-   安装（或确认安装）所需的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 激活组件。  
  
-   创建一个具有要使用的网络协议绑定的 WAS 站点，或者向现有站点添加新协议绑定。  
  
-   创建一个应用程序以承载服务，并使该应用程序可以使用所需的网络协议。  
  
-   生成一个公开非 HTTP 终结点的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。  
  
## <a name="configuring-a-site-with-non-http-bindings"></a>使用非 HTTP 绑定配置站点  
 若要将非 HTTP 绑定与 WAS 一起使用，必须将站点绑定添加到 WAS 配置。 WAS 的配置存储是 applicationHost.config 文件，该文件位于 %windir%\system32\inetsrv\config 目录中。 此配置存储由 WAS 和 IIS 7.0 共享。  
  
 applicationHost.config 是一个 XML 文本文件，可以使用任何标准文本编辑器（如记事本）打开。 不过，[!INCLUDE[iisver](../../../../includes/iisver-md.md)] 命令行配置工具 (appcmd.exe) 是添加非 HTTP 站点绑定的首选方法。  
  
 下面的命令使用 appcmd.exe 将 net.tcp 站点绑定添加到默认网站（将此命令作为单独的一行输入）。  
  
```  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 通过将下面指示的行添加到 applicationHost.config 文件，此命令将新 net.tcp 绑定添加到默认网站。  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
        <bindings>  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            //The following line is added by the command.  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
        </bindings>  
    </site>  
</sites>  
```  
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a>使应用程序可以使用非 HTTP 协议  
 你可以启用或禁用单个网络 protocolsat 应用程序级别。 下面的命令说明如何为在 `Default Web Site` 中运行的应用程序同时启用 HTTP 和 net.tcp 协议。  
  
```  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 也可以在设置启用的协议列表\<applicationDefaults > 在 ApplicationHost.config 中存储的站点的 XML 配置元素。  
  
 摘自 applicationHost.config 的以下 XML 代码说明一个已同时绑定到 HTTP 协议和非 HTTP 协议的站点。 支持非 HTTP 协议所需的其他配置通过注释进行了突出。  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
    <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
    </application>  
       <bindings>  
            //The following two lines are added by the command.  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
       </bindings>  
    </site>  
    <siteDefaults>  
        <logFile   
        customLogPluginClsid="{FF160663-DE82-11CF-BC0A-00AA006111E0}"  
          directory="D:\inetpub\logs\LogFiles" />  
        <traceFailedRequestsLogging   
          directory="D:\inetpub\logs\FailedReqLogFiles" />  
    </siteDefaults>  
    <applicationDefaults   
      applicationPool="DefaultAppPool"   
      //The following line is inserted by the command.  
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 如果您尝试通过用于非 HTTP 激活的 WAS 来激活服务，并且您未安装和配置 WAS，您可能会看到以下错误：  
  
```Output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 如果您看到此错误，确保已安装并正确配置了用于非 HTTP 激活的 WAS。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][如何： 安装和配置 WCF 激活组件](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)。  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a>生成一个将 WAS 用于非 HTTP 激活的 WCF 服务  
 一旦执行的步骤来安装和配置 WAS (请参阅[如何： 安装和配置 WCF 激活组件](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md))，服务配置为使用 WAS 激活是类似于在 IIS 中配置托管服务。  
  
 有关生成 WAS 激活的详细说明[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务，请参阅[如何： 承载在 WAS 中的 WCF 服务](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)。  
  
## <a name="see-also"></a>另请参阅  
 [在 Windows Process Activation Service 中承载](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)  
 [Windows Server App Fabric 承载功能](http://go.microsoft.com/fwlink/?LinkId=201276)
