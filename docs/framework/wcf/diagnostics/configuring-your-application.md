---
title: 配置应用程序
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 4e19e4d0ecb6bc90402f99dddd280ee1dbcf7ea0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798148"
---
# <a name="configuring-your-application"></a>配置应用程序
Windows Communication Foundation （WCF）使用 .NET 配置系统，并允许你在计算机和应用程序范围中配置服务。  
  
 WCF 定义的配置设置位于`<system.serviceModel>`节组中。 有关如何配置 WCF 服务的详细信息，请参阅以下主题：  
  
- [配置服务](../configuring-services.md)  
  
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 应用程序定义的配置设置是在 `<appSettings>` 节组中定义的。 有关 .net 配置文件中的应用程序设置的详细信息，请参阅[ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159)。  
  
## <a name="using-the-configuration-editor"></a>使用配置编辑器  
 使用 WCF[配置编辑器工具（svcconfigeditor.exe）](../configuration-editor-tool-svcconfigeditor-exe.md) ，管理员和开发人员可以使用图形用户界面来创建和修改 WCF 服务的配置设置。 利用此工具，无需直接编辑 XML 配置文件，即可管理 WCF 绑定、行为、服务和诊断的设置。  
  
## <a name="editing-configuration-files-in-visual-studio"></a>在 Visual Studio 中编辑配置文件  
 若要在 Visual Studio 中编辑 WCF 服务项目的配置文件，请在**解决方案资源管理器**中右键单击该项目，然后选择 "**编辑 WCF 配置**" 上下文菜单项。 这将启动[配置编辑器工具（svcconfigeditor.exe）](../configuration-editor-tool-svcconfigeditor-exe.md)。  
  
> [!NOTE]
> 如果你在 Visual Studio 中编辑 WCF Web Services 项目的配置文件，请在**解决方案资源管理器**中右键单击该项目，请注意，"**编辑 wcf 配置**" 上下文菜单项缺失。 若要解决此问题，请单击 "**工具**" 菜单，然后选择 " **WCF 服务配置编辑器**"。 之后，您可以右键单击某个配置文件并使用 "**编辑 WCF 配置**" 上下文菜单项。  
  
## <a name="see-also"></a>请参阅

- [配置编辑器工具 (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)
- [配置服务](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
