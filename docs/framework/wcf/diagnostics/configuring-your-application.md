---
title: 配置应用程序
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 39d8c73809b8c2695ccebb1d69d1c016fd2313d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584631"
---
# <a name="configuring-your-application"></a><span data-ttu-id="84040-102">配置应用程序</span><span class="sxs-lookup"><span data-stu-id="84040-102">Configuring Your Application</span></span>
<span data-ttu-id="84040-103">Windows Communication Foundation (WCF) 使用.NET 配置系统，并且允许您在计算机和应用程序范围配置服务。</span><span class="sxs-lookup"><span data-stu-id="84040-103">Windows Communication Foundation (WCF) uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="84040-104">定义的 WCF 配置设置位于`<system.serviceModel>`节组。</span><span class="sxs-lookup"><span data-stu-id="84040-104">Configuration settings defined by WCF are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="84040-105">有关如何配置 WCF 服务的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="84040-105">For more information about how to configure a WCF service, see the following topics:</span></span>  
  
-   [<span data-ttu-id="84040-106">配置服务</span><span class="sxs-lookup"><span data-stu-id="84040-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [<span data-ttu-id="84040-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="84040-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="84040-108">应用程序定义的配置设置是在 `<appSettings>` 节组中定义的。</span><span class="sxs-lookup"><span data-stu-id="84040-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="84040-109">有关.NET 配置文件中的应用程序设置的详细信息，请参阅[ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159)。</span><span class="sxs-lookup"><span data-stu-id="84040-109">For more information about application settings in .NET configuration files, see [\<appSettings>](https://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="84040-110">使用配置编辑器</span><span class="sxs-lookup"><span data-stu-id="84040-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="84040-111">WCF[配置编辑器工具 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)使管理员和开发人员能够创建和修改 WCF 服务使用的图形用户界面的配置设置。</span><span class="sxs-lookup"><span data-stu-id="84040-111">The WCF [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="84040-112">利用此工具，可以管理 WCF 绑定、 行为、 服务和诊断的设置，而无需直接编辑 XML 配置文件。</span><span class="sxs-lookup"><span data-stu-id="84040-112">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="84040-113">在 Visual Studio 中编辑配置文件</span><span class="sxs-lookup"><span data-stu-id="84040-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="84040-114">若要编辑的 Visual Studio 中的 WCF 服务项目的配置文件，右键单击它以**解决方案资源管理器**，然后选择**编辑 WCF 配置**上下文菜单项。</span><span class="sxs-lookup"><span data-stu-id="84040-114">To edit the configuration file of a WCF service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="84040-115">这将启动[配置编辑器工具 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="84040-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84040-116">如果右键单击该中编辑配置文件的 Visual Studio 中的 WCF Web 服务项目**解决方案资源管理器**，注意**编辑 WCF 配置**上下文菜单项缺少。</span><span class="sxs-lookup"><span data-stu-id="84040-116">If you edit the configuration file of a WCF Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="84040-117">解决此问题，请单击**工具**菜单，然后选择**WCF 服务配置编辑器**。</span><span class="sxs-lookup"><span data-stu-id="84040-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="84040-118">之后，可以右键单击配置文件，并使用**编辑 WCF 配置**上下文菜单项。</span><span class="sxs-lookup"><span data-stu-id="84040-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84040-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="84040-119">See also</span></span>
- [<span data-ttu-id="84040-120">配置编辑器工具 (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="84040-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="84040-121">配置服务</span><span class="sxs-lookup"><span data-stu-id="84040-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="84040-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="84040-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
