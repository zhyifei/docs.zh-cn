---
title: 使用 Windows 通信基础教程对入门进行故障排除
ms.date: 01/25/2019
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 92e986370fe1b6e067d9f8aebc73179c1ac6a20f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183091"
---
# <a name="troubleshoot-the-get-started-with-windows-communication-foundation-tutorials"></a>使用 Windows 通信基础教程对入门进行故障排除

本文提供了解决方案，解决在按照[教程中的步骤：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)时可能面临的最常见问题和错误。
  
## <a name="common-problems"></a>常见问题

**我在硬盘上找不到项目文件。**

 Visual Studio 将项目文件保存在*C：\用户\\&lt;用户名&gt;[源]存储库*中。  

**我找不到*Svcutil.exe*生成的*App.config*文件。**

 在 Visual Studio 中，"**添加现有项目"** 窗口默认仅显示具有以下扩展名的文件：

- *.cs*
- *.resx*
- *.设置*
- *.xsd*
- *.wsdl*

要显示所有文件类型，请在 **"添加现有项目**"窗口右下角的下拉列表中选择 **"所有文件 "（.）。\*\***  
  
## <a name="common-errors"></a>常见错误

### <a name="compile-the-service-application"></a>编译服务应用程序

**在"入门主机.模块1"中未找到错误 BC30420"子主"。**

对于可视化基本应用程序，入口点不正确。 进行以下更改：

   1. 在 **"解决方案资源管理器"** 窗口中，选择 **"入门主机"** 文件夹，然后从快捷菜单中选择 **"属性**"。
    a.在“解决方案资源管理器”中，右键单击项目文件夹下的“引用”文件夹，然后单击“添加引用”。 在 **"入门主机"** 窗口中，对于**启动对象**，从列表中选择 **"服务.程序**"（或特定应用程序的入口点）。
    b.保留“数据库类型”设置，即设置为“共享”。 从主菜单中，选择 **"全部保存文件** > **Save All**"。

### <a name="run-the-service-application"></a>运行服务应用程序

**HTTP 无法注册 URL "http：\//：8000/入门/计算器服务"。您的进程没有对此命名空间的访问权限。**

 要获得适当的访问权限，可以启动托管具有管理权限的 Windows 通信基础 （WCF） 服务的过程：

- 对于可视化工作室：在 **"开始"** 菜单中选择"视觉工作室"程序，然后从快捷菜单中选择 **"以管理员** > **身份运行**更多"。
- 对于控制台窗口：在 **"开始"** 菜单中选择 **"命令提示"，** 然后从快捷菜单中选择 **"以** > **管理员身份运行**更多"。
- 对于 Windows 资源管理器：选择可执行文件，然后从快捷菜单中选择 **"以管理员身份运行**"。

### <a name="compile-the-client-application"></a>编译客户端应用程序

**"计算器客户端"，不包含"方法名称>"\<的定义，并且找不到接受类型为"计算器客户端\<"的第一个参数的扩展方法"方法名称>"（您是否缺少使用指令或程序集引用？**  

只有使用`ServiceOperationAttribute`属性标记的方法才会公开。 如果在`ICalculator`接口中的方法省略`ServiceOperationAttribute`该属性，则会在编译期间收到此错误消息。  

**找不到类型或命名空间名称"计算器客户端"（您是否缺少 using 指令或程序集引用？**

 如果在使用*Svcutil.exe*工具生成*generatedProxy.cs（* 或*生成的Proxy.vb）* 文件时，未将这些文件添加到客户端项目中，则收到此错误。  

### <a name="run-the-client-application"></a>运行客户端应用程序

**未处理异常：系统.服务模型.终结点未找到异常：无法连接到"http：/\/本地主机：8000/入门/计算器服务"。TCP 错误代码 10061：由于目标计算机主动拒绝，因此无法进行连接。**

如果在未首次启动服务的情况下运行客户端应用程序，则会发生此错误。 首先，运行主机应用程序以启动服务，然后运行客户端应用程序。

### <a name="use-the-svcutilexe-tool"></a>使用 Svcutil.exe 工具

**"Svcutil"不被识别为内部或外部命令、可操作程序或批处理文件。**

 *Svcutil.exe*必须位于系统路径中。 最简单的解决方案是使用 Visual Studio 命令提示符。 在 **"开始"** 菜单中，选择 **"\<视觉工作室"版本>** 目录，然后选择 **"开发人员\<命令提示">。 ** 此命令提示符将系统路径设置到作为 Visual Studio 一部分提供的所有工具的正确位置。  
  
### <a name="run-the-service-and-client-applications"></a>运行服务和客户端应用程序

**系统.服务模型.安全.安全协商例外：SOAP 安全协商与目标的"http：/localhost：8000/\/入门/计算器服务"的目标"http：/localhost：8000/\/入门/计算器服务"失败**  

此错误发生在没有网络连接的域加入计算机上。 将计算机连接到网络或关闭服务和客户端的安全性。

要关闭安全性：

- 对于服务，用以下代码替换创建`WSHttpBinding`的代码：  
  
    ```csharp
    // Step 3: Add a service endpoint.
    selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
    ```

- 对于客户端，在配置文件中，在**\<绑定>** 元素下更新**\<安全>** 元素，如下所示：  
  
    ```xml
    <binding name="WSHttpBinding_ICalculator" security mode="None" />
    ```  

## <a name="see-also"></a>另请参阅  
 [开始使用 WCF 应用程序](getting-started-tutorial.md)  
 [WCF 故障排除快速入门](wcf-troubleshooting-quickstart.md)  
 [排除设置问题](troubleshooting-setup-issues.md)
