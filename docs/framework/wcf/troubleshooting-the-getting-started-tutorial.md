---
title: 入门教程疑难解答
ms.date: 03/30/2017
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 5b8cd04ef4d98e522e255e1b7529e848351b2e0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695655"
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>入门教程疑难解答
本主题列出使用“入门教程”时最常遇见的问题及其解决方法。  
  
**我找不到我的硬盘驱动器上的项目文件。**

 Visual Studio 将项目文件保存在 c:\users\\<user name>\Documents\\< Visual Studio 版本\>\Projects。  
  
**尝试运行服务应用程序：HTTP 无法注册 URL `http://+:8000/ServiceModelSamples/Service/`。**
**进程不具有此命名空间的访问权限。** 

 承载 WCF 服务的进程必须使用管理权限运行。 如果您正在运行该服务从在 Visual Studio 中，您必须运行 Visual Studio 以管理员身份。 若要执行操作，请单击**启动**，右键单击**Visual Studio \<*版本*>**  ，然后选择**以管理员身份运行**. 如果从控制台窗口中的命令行提示符下运行该服务，则必须以管理员身份启动控制台窗口，类似的方式。 单击**启动**，右键单击**命令提示符**，然后选择**以管理员身份运行**。  
  
**尝试使用 Svcutil.exe 工具: svcutil 不被识别为内部或外部命令、 可操作程序或批处理文件。**

 Svcutil.exe 必须位于系统路径中。 最简单的解决方案是使用命令提示符。 单击**启动**，选择**所有程序**， **Visual Studio \<*版本*>**， **Visual Studio 工具**，并**Visual Studio 的开发人员命令提示**。 此命令提示符下设置为正确的位置的 Visual Studio 中附带的所有工具的系统路径。  

**无法找到由 Svcutil.exe 生成的 App.config 文件。**

 **添加现有项**对话框仅显示默认情况下具有以下扩展名的文件：.cs、.resx、.settings、.xsd 和.wsdl。 您可以指定你想要通过选择查看所有文件类型**的所有文件 (\*。\*)** 中的下拉列表框中的右下角**添加现有项**对话框。  


**编译客户端应用程序：CalculatorClient 不包含的定义\<方法名称 > 和扩展方法\<方法名称 > 接受的第一个参数的类型找不到 CalculatorClient (是否缺少 using 指令或程序集引用？）**  

仅向外界公开标记有 `ServiceOperationAttribute` 的那些方法。 如果您省略`ServiceOperationAttribute`属性中的方法之一从`ICalculator`接口，您可以收到此错误消息，编译以下位置缺少该属性的操作调用的客户端应用程序时。  

**编译客户端应用程序：找不到 CalculatorClient 的类型或命名空间名称 (是否缺少 using 指令或程序集引用？)**

 如果未将 Proxy.cs 或 Proxy.vb 文件添加到客户端项目，则会收到此错误。  

**运行客户端：未经处理的异常：System.ServiceModel.EndpointNotFoundException:无法连接到`http://localhost:8000/ServiceModelSamples/Service/CalculatorService`。TCP 错误代码 10061:由于目标机器主动拒绝，无法建立连接。**

如果在未运行服务的情况下运行客户端应用程序，则会出现此错误。  
  
**未经处理的异常：System.ServiceModel.Security.SecurityNegotiationException:与 SOAP 安全协商`http://localhost:8000/ServiceModelSamples/Service/CalculatorService`目标`http://localhost:8000/ServiceModelSamples/Service/CalculatorService`失败**  

此错误发生在已加入域但没有网络连接的计算机上。 将计算机连接到网络，或者同时关闭客户端和服务的安全性。 对于服务，将创建 WSHttpBinding 的代码修改为以下代码。  
  
```csharp
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```

对于客户端，更改**\<安全 >** 元素下的**\<绑定 >** 以下元素：  
  
```xml
<security mode="Node" />  
```  

## <a name="see-also"></a>请参阅
- [入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)
- [WCF 疑难解答快速入门](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)
- [安装问题疑难解答](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
