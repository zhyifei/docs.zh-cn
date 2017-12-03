---
title: "配置应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 064f396d0a757e5b2f5f12c4a2a836b74f5e66a6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-your-application"></a><span data-ttu-id="5f779-102">配置应用程序</span><span class="sxs-lookup"><span data-stu-id="5f779-102">Configuring Your Application</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="5f779-103"> 使用 .NET 配置系统并允许您在计算机和应用程序范围配置服务。</span><span class="sxs-lookup"><span data-stu-id="5f779-103"> uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="5f779-104">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 定义的配置设置位于 `<system.serviceModel>` 节组中。</span><span class="sxs-lookup"><span data-stu-id="5f779-104">Configuration settings defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are located in the `<system.serviceModel>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5f779-105">如何配置 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务，请参见以下主题：</span><span class="sxs-lookup"><span data-stu-id="5f779-105"> how to configure a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see the following topics:</span></span>  
  
-   [<span data-ttu-id="5f779-106">配置服务</span><span class="sxs-lookup"><span data-stu-id="5f779-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [<span data-ttu-id="5f779-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5f779-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="5f779-108">应用程序定义的配置设置是在 `<appSettings>` 节组中定义的。</span><span class="sxs-lookup"><span data-stu-id="5f779-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5f779-109">应用程序设置中.NET 配置文件，请参阅[ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159)。</span><span class="sxs-lookup"><span data-stu-id="5f779-109"> application settings in .NET configuration files, see [\<appSettings>](http://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="5f779-110">使用配置编辑器</span><span class="sxs-lookup"><span data-stu-id="5f779-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="5f779-111">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)][配置编辑器工具 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)允许管理员和开发人员创建和修改配置设置[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务使用图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="5f779-111">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)][Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using a graphical user interface.</span></span> <span data-ttu-id="5f779-112">利用此工具，您无需直接编辑 XML 配置文件就可管理 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 绑定、行为、服务和诊断的设置。</span><span class="sxs-lookup"><span data-stu-id="5f779-112">With this tool, you can manage settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="5f779-113">在 Visual Studio 中编辑配置文件</span><span class="sxs-lookup"><span data-stu-id="5f779-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="5f779-114">若要编辑的配置文件[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]中的服务项目[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]，右键单击在**解决方案资源管理器**选择**编辑 WCF 配置**上下文菜单项。</span><span class="sxs-lookup"><span data-stu-id="5f779-114">To edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="5f779-115">这将启动[配置编辑器工具 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="5f779-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f779-116">如果编辑的配置文件[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]中的 Web 服务项目[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]，右键单击该中**解决方案资源管理器**，请注意，**编辑 WCF 配置**未提供的上下文菜单项.</span><span class="sxs-lookup"><span data-stu-id="5f779-116">If you edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Service project in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="5f779-117">解决此问题，请单击**工具**菜单上，选择**WCF 服务配置编辑器**。</span><span class="sxs-lookup"><span data-stu-id="5f779-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="5f779-118">之后，你可以右键单击配置文件并使用**编辑 WCF 配置**上下文菜单项。</span><span class="sxs-lookup"><span data-stu-id="5f779-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f779-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f779-119">See Also</span></span>  
 [<span data-ttu-id="5f779-120">配置编辑器工具 (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="5f779-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [<span data-ttu-id="5f779-121">配置服务</span><span class="sxs-lookup"><span data-stu-id="5f779-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="5f779-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5f779-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
