---
title: ASP.NET 客户端中的数据绑定
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: c068c1cab5a5b9dad75e781e58076f4066a3b2a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145002"
---
# <a name="data-binding-in-an-aspnet-client"></a>ASP.NET 客户端中的数据绑定
此示例演示如何在 Web 窗体应用程序中绑定典型 Windows 通信基础 （WCF） 服务返回的数据。  
  
> [!NOTE]
> 本主题的最后介绍了此示例的设置过程和生成说明。  
  
 本示例演示一个服务，该服务可实现定义“请求-答复”通信模式的协定。 该示例包括可从浏览器访问的客户端 Web 窗体应用程序和由 Internet 信息服务 （IIS） 托管的 WCF 服务。  
  
 该服务实现定义“请求-答复”通信模式的协定。 协定由 `IWeatherService` 接口定义，该接口公开一个名为 `GetWeatherData` 的操作。 此操作接受一个城市数组并返回一个 `WeatherData` 对象数组，这些对象表示城市的预报高温和预报低温。  
  
 在ASP.NET客户端 .aspx 页上，定义了 DataGrid Web 控件，其中包含服务返回的数据的图形表示形式。 .aspx 页上的代码调用 WCF 服务以访问天气数据，并将数据返回到`WeatherData`对象数组。 DataGrid 通过将它的 `DataSource` 属性设置为该数组来指定从何处获取数据。 数据绑定通过调用 DataGrid 的 `DataBind` 方法发生。 所有这些代码都包含在 中。`aspx` 页面`Page_Load`的方法，因此每次用户刷新浏览器页面时，数据都会在 DataGrid 中更新。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3. 本示例的客户端是运行在开发 Web 服务器下的网站。 要启动开发 Web 服务器，在命令提示符下键入以下内容`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`： 。 然后浏览到`http://localhost:8000/client`。 若要跨计算机运行此示例，请在客户端的 Web.config 文件中将所有对 `localhost` 的引用替换为服务器的计算机名称。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`
