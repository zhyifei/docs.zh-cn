---
title: 排查 Windows Communication Foundation 教程入门
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 10a2f8f718d802a7aab067b882f0d5cf3dc28dca
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928583"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>排查 Windows Communication Foundation 教程入门

本文提供了有关在执行[教程中的步骤时可能会遇到的最常见问题和错误的解决方案：开始 Windows Communication Foundation 应用程序](getting-started-tutorial.md)。 
  
## <a name="common-problems"></a>常见问题

**我在硬盘驱动器上找不到项目文件。**

 Visual Studio 将项目文件保存*在\\C:\Users&lt;用户名&gt;\source\repos*中。  

**找不到*svcutil.exe*生成的*app.config*文件。**

 在 Visual Studio 中，默认情况下，"**添加现有项**" 窗口仅显示具有以下扩展名的文件： 

- .cs 
- *.resx* 
- *.settings*
- *.xsd* 
- *.wsdl*

若要显示所有文件类型，请选择 **的所有文件 (\*。\*)** 右下角的下拉列表中**添加现有项**窗口。  
  
## <a name="common-errors"></a>常见错误

### <a name="compile-the-service-application"></a>编译服务应用程序 

**在 "GettingStartedHost" 中找不到 "Sub Main" 错误 BC30420。**

Visual Basic 应用程序的入口点不正确。 进行以下更改：

   1. 在 "**解决方案资源管理器**" 窗口中，选择 " **GettingStartedHost** " 文件夹，然后从快捷菜单中选择 "**属性**"。
    a. 在 " **GettingStartedHost** " 窗口中，对于 "**启动对象**"，从列表中选择 "**服务**" （或特定应用程序的入口点）。 
    b. 在主菜单中，选择 "**文件** > " "**全部保存**"。

### <a name="run-the-service-application"></a>运行服务应用程序 

**Http 无法注册 URL "http：\//+： 8000/GettingStarted/CalculatorService"。进程不具有此命名空间的访问权限。** 

 若要进行适当的访问，请使用管理权限启动承载 Windows Communication Foundation （WCF）服务的进程：

- 对于 Visual Studio：在 "**开始**" 菜单中选择 "Visual Studio" 程序，然后从快捷菜单中选择 "**更多** > **运行方式管理员**"。
- 对于控制台窗口：选择 "**开始**" 菜单中的 "**命令提示符**"，然后从快捷菜单中选择 "**更多** > **运行方式管理员**"。
- 对于 Windows 资源管理器：选择可执行文件，然后从快捷菜单中选择 "**以管理员身份运行**"。

### <a name="compile-the-client-application"></a>编译客户端应用程序

**"CalculatorClient" 不包含 "\<method name >" 的定义，并且找不到可接受类型为 "CalculatorClient" 的第一个参数的扩展方法 "\<method name > （是否缺少 using 指令或程序集引用？）**  

仅公开了用`ServiceOperationAttribute`特性标记的那些方法。 如果在`ICalculator`接口中`ServiceOperationAttribute`省略方法中的属性，则会在编译过程中收到此错误消息。  

**找不到类型或命名空间名称 "CalculatorClient" （是否缺少 using 指令或程序集引用？）**

 如果你在生成包含*svcutil.exe*工具的*GeneratedProxy.cs* （或*generatedProxy*）时未将该文件添加到客户端项目，则会收到此错误。  

### <a name="run-the-client-application"></a>运行客户端应用程序

**未经处理的异常：System.ServiceModel.EndpointNotFoundException:无法连接到 "http：\//localhost： 8000/GettingStarted/CalculatorService"。TCP 错误代码10061：由于目标计算机主动拒绝，因此无法建立连接。**

如果在不首先启动服务的情况下运行客户端应用程序，则会发生此错误。 首先，运行主机应用程序以启动该服务，然后运行客户端应用程序。

### <a name="use-the-svcutilexe-tool"></a>使用 Svcutil.exe 工具
   
**"Svcutil.exe" 未被识别为内部或外部命令、可使用的程序或批处理文件。**

 *Svcutil.exe*必须在系统路径中。 最简单的解决方案是使用 Visual Studio 命令提示符。 从 "**开始**" 菜单中，选择 " **Visual Studio \<版本 >** " 目录，然后选择 "**开发人员命令提示" 用于 VS \<版本 >** 。 对于作为 Visual Studio 的一部分提供的所有工具，此命令提示符将系统路径设置为正确的位置。  
  
### <a name="run-the-service-and-client-applications"></a>运行服务和客户端应用程序

**System.ServiceModel.Security.SecurityNegotiationException:对于目标 "http：\/\//localhost： 8000/GettingStarted/CalculatorService"，具有 "http：/localhost： 8000/GettingStarted/CalculatorService" 的 SOAP 安全协商失败**  

此错误发生在未建立网络连接的已加入域的计算机上。 将计算机连接到网络，或关闭服务和客户端的安全性。 

关闭安全：

- 对于服务，请将创建的`WSHttpBinding`代码替换为以下代码：  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- 对于客户端配置文件中更新 **\<安全>** 元素下的 **\<绑定 >** 元素，如下所示：  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>请参阅  
 [WCF 应用程序入门](getting-started-tutorial.md)  
 [WCF 疑难解答快速入门](wcf-troubleshooting-quickstart.md)  
 [安装问题疑难解答](troubleshooting-setup-issues.md)
