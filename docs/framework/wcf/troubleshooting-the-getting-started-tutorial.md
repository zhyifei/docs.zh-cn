---
title: "入门教程疑难解答"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f7372aab9e728876a6127eb49e1594ac50810c99
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>入门教程疑难解答
本主题列出使用“入门教程”时最常遇见的问题及其解决方法。  
  
1.  [我找不到我的硬盘驱动器上的项目文件。](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [尝试运行服务应用程序时出现以下错误：HTTP 无法注册 URL http://+:8000/ServiceModelSamples/Service/。进程不具有此命名空间的访问权限。](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [尝试使用 Svcutil.exe 工具: svcutil 不识别为内部或外部命令、 可操作程序或批处理文件。](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [找不到由 Svcutil.exe 生成的 App.config 文件。](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [编译客户端应用程序: CalculatorClient 不包含的定义&lt;方法名称&gt;和扩展方法&lt;方法名称&gt;接受类型为 CalculatorClient 的第一个自变量找不到 (是否缺少 using 指令或程序集引用？)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [编译客户端应用程序： 找不到 CalculatorClient 的类型或命名空间名称 (是否缺少 using 指令或程序集引用？)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [运行客户端： 未经处理的异常： System.ServiceModel.EndpointNotFoundException： 无法连接到： //localhost: 8000/ServiceModelSamples/Service/CalculatorService。TCP 错误代码 10061： 由于目标计算机主动拒绝，无法建立连接。](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## <a name="i-am-unable-to-find-the-project-files-on-my-hard-drive"></a>无法在硬盘上找到项目文件。  
 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]将项目 c:\users 中的文件保存\\< 用户 name\Documents\\< Visual Studio 版本\>中的 \Projects[!INCLUDE[wv](../../../includes/wv-md.md)]和[!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)]，和 c:\Documents and Settings\\< 用户名\>\My documents\\< Visual Studio 版本\>\Projects 在早期版本的 Windows。  
  
<a name="BKMK_q2"></a>   
## <a name="attempting-to-run-the-service-application-http-could-not-register-url-http8000servicemodelsamplesservice-your-process-does-not-have-access-rights-to-this-namespace"></a>尝试运行服务应用程序时出现以下错误：HTTP 无法注册 URL http://+:8000/ServiceModelSamples/Service/。 进程不具有此命名空间的访问权限。  
 必须使用管理特权来运行承载 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务的进程。 如果从 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 内运行服务，则必须以管理员身份运行 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]。 为此，请单击**启动**，右键单击[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]和选择**以管理员身份运行**。 如果从命令行提示符运行服务，则必须按类似方式以管理员身份启动命令行提示符。 单击**启动**，右键单击**命令提示符**和选择**以管理员身份运行**。  
  
<a name="BKMK_q3"></a>   
## <a name="attempting-to-use-the-svcutilexe-tool-svcutil-is-not-recognized-as-an-internal-or-external-command-operable-program-or-batch-file"></a>尝试使用 Svcutil.exe 工具时出现以下错误：“svcutil”不是内部或外部命令，也不是可操作的程序或批处理文件。  
 Svcutil.exe 必须位于系统路径中。 最简单的解决方案是使用命令提示符。 单击**启动**，选择**所有程序**， [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]， **Visual Studio Tools**，和[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]**命令提示符**。 对于 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中附带的所有工具，此命令提示均能将系统路径设置为正确的位置。  
  
<a name="BKMK_q4"></a>   
## <a name="unable-to-find-the-appconfig-file-generated-by-svcutilexe"></a>无法找到由 Svcutil.exe 生成的 App.config 文件。  
 **添加现有项**对话框仅显示默认情况下具有以下扩展名的文件：.cs、.resx、.settings、.xsd、.wsdl。 你可以指定你想要通过选择查看所有文件类型**所有文件 (\*。\*)**的下拉列表框中的右下角中**添加现有项**对话框。  
  
<a name="BKMK_q5"></a>   
## <a name="compiling-the-client-application-calculatorclient-does-not-contain-a-definition-for-method-name-and-no-extension-method-method-name-accepting-a-first-argument-of-type-calculatorclient-could-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>编译客户端应用程序: CalculatorClient 不包含的定义\<方法名称 > 和扩展方法\<方法名称 > 接受的第一个参数的类型为 CalculatorClient 找不到 （是否缺少 using 指令或程序集引用？)  
 仅向外界公开标记有 `ServiceOperationAttribute` 的那些方法。 如果在 `ServiceOperationAttribute` 接口的某个方法中省略了 `ICalculator` 属性，则当所编译的客户端应用程序调用缺少该属性的操作时，便会收到此错误消息。  
  
<a name="BKMK_q6"></a>   
## <a name="compiling-the-client-application-the-type-or-namespace-name-calculatorclient-could-not-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>编译客户端应用程序期间出现以下错误：找不到类型或命名空间名称“CalculatorClient”(是否缺少 using 指令或程序集引用?)  
 如果未将 Proxy.cs 或 Proxy.vb 文件添加到客户端项目，则会收到此错误。  
  
<a name="BKMK_q7"></a>   
## <a name="running-the-client-unhandled-exception-systemservicemodelendpointnotfoundexception-could-not-connect-to-httplocalhost8000servicemodelsamplesservicecalculatorservice-tcp-error-code-10061-no-connection-could-be-made-because-the-target-machine-actively-refused-it"></a>运行客户端期间出现以下错误：未处理的异常: System.ServiceModel.EndpointNotFoundException: 无法连接到 http://localhost:8000/ServiceModelSamples/Service/CalculatorService。 TCP 错误代码 10061: 由于目标计算机主动拒绝，未能建立连接。  
 如果在未运行服务的情况下运行客户端应用程序，则会出现此错误。  
  
<a name="BKMK_q8"></a>   
## <a name="unhandled-exception-systemservicemodelsecuritysecuritynegotiationexception-soap-security-negotiation-with-httplocalhost8000servicemodelsamplesservicecalculatorservice-for-target-httplocalhost8000servicemodelsamplesservicecalculatorservice-failed"></a>未处理的异常: System.ServiceModel.Security.SecurityNegotiationException: 目标“http://localhost:8000/ServiceModelSamples/Service/CalculatorService”与“http://localhost:8000/ServiceModelSamples/Service/CalculatorService”的 SOAP 安全协商失败  
 此错误发生在已加入域但没有网络连接的计算机上。 将计算机连接到网络，或者同时关闭客户端和服务的安全性。 对于服务，将创建 WSHttpBinding 的代码修改为以下代码。  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```  
  
 对于客户端上，更改**\<安全 >**元素下的**\<绑定 >**将以下元素：  
  
```xml  
<security mode="Node" />  
```  
  
## <a name="see-also"></a>另请参阅  
 [入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [WCF 疑难解答快速入门](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 [安装问题疑难解答](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
