---
title: WCF 服务发布
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: 258c7e65b69648477e58880f35b100a9378dc9c0
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806456"
---
# <a name="wcf-service-publishing"></a>WCF 服务发布
Windows Communication Foundation (WCF) 服务发布可帮助你从由 WCF 服务主机和 WCF 测试客户端提供到实际将部署到生产环境中以进行测试应用程序的早期开发环境的进展情况。 在提交最终部署计划之前，你可以使用 Windows Communication Foundation (WCF) 服务发布来验证您的 WCF 服务正常运行，以及已准备好发布。 你还可以选择将你的 WCF 服务库部署到用于测试的各种目标位置。  
  
## <a name="supported-services-and-target-locations"></a>支持的服务和目标位置  
 WCF 服务发布支持发布 WCF 服务创建的 WCF 服务库模板以及其对应的项模板，其中包括以下各项：  
  
-   带有项模板的 WCF 服务库模板。  
  
-   联合服务库。  
  
 你可以通过选择找到这些服务模板**文件** -> **新项目** -> **Visual Basic**或**Visual C#**  ->  **WCF**。 在此位置 （包括 WCF 工作流服务应用程序和 WCF 服务应用程序） 的其他 WCF 模板可以发布使用[一键式发布为 web 应用程序](https://msdn.microsoft.com/library/dd465337\(v=vs.110\).aspx)。  
  
 可以将服务发布到以下目标位置。  
  
-   本地 IIS。  
  
-   文件系统。  
  
-   FTP 站点。  
  
## <a name="using-wcf-service-publishing"></a>使用 WCF 服务发布  
 若要部署服务实现，请执行以下步骤：  
  
1.  使用提升的特权打开 Visual Studio （右键单击可执行文件和使用"以管理员身份运行"以启动它）。  如果你使用的 IIS 7.0 或更高版本，请确保你已安装"IIS 元数据库和 iis 6 配置兼容性"组件使用"打开或关闭 Windows 功能"控制面板中。  
  
2.  打开服务项目中，选择**生成**->**发布\<项目名称 >** 从主菜单中，右键单击中的项目或**解决方案资源管理器**单击**发布**。  
  
3.  **发布**窗口随即显示。 单击 **...**. 按钮指定服务应部署到的目标位置。 你可以选择将应用部署到本地 IIS、 文件系统或 FTP 站点。 如果部署到本地 IIS 应用程序，你可以选择你的网站，并通过单击创建 web 应用程序在其下**创建新的 Web 应用程序**在右上角的图标。  
  
4.  单击后**发布**主窗口中，在 Visual Studio 部署到指定的目标位置的应用程序，并将 Web.config、.svc 和程序集文件复制到目标目录。 . .Svc 的名称将为"ProjectName.ServiceName.svc"。 已成功发布服务后，可以在 Visual Studio 输出窗口中，其外观类似于"正在连接到超链接"中找到一个热链接http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName ..."。 可在按住 Ctrl 键的同时单击该链接来打开 Visual Studio 中的浏览器页面，以便查看服务目录结构。  
  
     如果您无法浏览到网站，这可能是因为 IIS 中未启用目录浏览器。 请按照要启用它的"可尝试的方法"部分中的提示。 或者，你可以直接键入"超链接"http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc"来查看服务页面。  
  
 你可以使用**发布**指定是否你想要复制程序集、 配置和目标位置，到项目中定义的所有服务的.svc 文件，并覆盖目标位置的现有文件。  
  
 如果选择将应用程序部署到本地 IIS，则可能会遇到与 IIS 设置有关的错误。 请确保已正确安装 IIS。 你可以键入"超链接"http://localhost" http://localhost"在浏览器并检查是否 IIS 默认页面时将显示。  此外可能在某些情况下，由在 IIS 中的不正确注册 ASP.NET 或 WCF 上导致问题。 你可以打开 Visual Studio 命令提示符并运行命令"aspnet_regiis.exe-ir"来解决 ASP.NET 注册问题，或运行命令"ServiceModelReg.exe – ia"来解决 WCF 注册问题。  
  
## <a name="files-generated-for-publishing"></a>生成的待发布文件  
 WCF 服务库可以由 Web 承载之前，由工具生成以下文件： 程序集文件、 Web.config 文件和.svc 文件。 这些文件全部复制到目标位置。 然后发布该服务。  
  
### <a name="assembly-files"></a>程序集文件  
 在发布的 WCF 服务时使用此工具，首先自动生成服务，并生成完毕后，在服务项目中的程序集文件生成。  
  
### <a name="svc-file"></a>.SVC 文件  
 发布操作生成每个 WCF 服务，一个 *.svc 文件，文件是否存在或不是，以确保版本有效性。 有两种不同的 svc 文件： 一个用于 WCF 服务库和联合服务库，另一种针对顺序和状态机工作流服务库。 生成\*.svc 文件复制到目标位置中的根文件夹。  
  
### <a name="webconfig-file"></a>Web.config 文件  
 每次将服务项目发布到特定目标位置时，都会创建一个 Web.config 文件。  
  
 生成的 Web.config 文件包括可用于 Web 托管，并包含以下更改的 WCF 服务库的 App.config 的内容的 Web 节：  
  
-   排除了基址。  
  
-   排除了 `<diagnostics>` 元素中的设置以保留目标平台的跟踪设置。  
  
## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>将具有非 HTTP 绑定的 WCF 服务发布到 IIS  
 如果你使用的是 iis 7.0 或更高版本，可以 WCF 服务发布到 IIS 的非 HTTP 绑定。 需要进行一些预配置。 有关详细信息，请参阅在主题[在 Windows 进程激活服务中承载](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)。  
  
## <a name="security"></a>安全性  
 发布到本地 IIS 需要具有管理员权限，原因是 IIS 要求以 Administrator 帐户身份运行。 如果用户没有管理员权限打开 WCF 服务发布，IIS 不可作为目标位置。 发布到文件系统或 FTP 站点的工作方式没有管理员权限。  
  
## <a name="see-also"></a>请参阅  
 [WCF Visual Studio 模板](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF 服务主机 (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF 测试客户端 (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
