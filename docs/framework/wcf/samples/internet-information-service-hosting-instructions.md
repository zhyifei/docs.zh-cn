---
title: "Internet 信息服务承载说明"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
caps.latest.revision: "30"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3c815ffe88918502f7d040bdeb1ff1b201cec832
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="internet-information-service-hosting-instructions"></a>Internet 信息服务承载说明
若要运行由 Internet 信息服务 (IIS) 承载的示例，必须确保 IIS 已正确安装且正在运行。  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a>在 Windows Server 2008 R2 上安装 IIS 7.5 版  
  
1.  从**服务器管理器**，选择**角色。** 下**角色摘要**，单击**添加角色**。  
  
2.  单击**下一步**以显示**选择服务器角色**对话框。  
  
3.  选择**应用程序服务器**从**角色**列表，，然后单击**下一步**两次以显示**选择角色服务**对话框应用程序服务器角色。  
  
4.  选择**Web 服务器 (IIS)**复选框。 如果系统提示你安装其他角色服务和功能，请单击**添加必需的功能**。 单击**下一步**两次以显示**选择角色服务**为 Web 服务器 (IIS) 角色的对话框。  
  
5.  展开**管理工具**，然后展开**IIS 6 管理兼容性**。 选择**IIS 6 脚本工具**。 如果系统提示你安装其他角色服务和功能，请单击**添加必需的角色服务**。 单击 **“下一步”**。  
  
6.  如果选项摘要正确无误，请单击**安装**。  
  
7.  当安装完成后时，单击**关闭**。  
  
### <a name="to-install-iis-version-75-on-windows-7"></a>在 Windows 7 上安装 IIS 7.5 版  
  
1.  单击**启动**，然后单击**控制面板**。  
  
2.  打开**程序**组。  
  
3.  下**程序和功能**，单击**打开或关闭 Windows 功能**。  
  
4.  **用户帐户控制**显示对话框。 单击 **“继续”**。  
  
5.  **Windows 功能**显示对话框。 展开项标记为**Internet Information Services**。  
  
6.  展开项标记为**World Wide Web 服务**。  
  
7.  展开项标记为**应用程序开发功能**。  
  
8.  请确保以下各项处于选中状态：  
  
    1.  **.NET 扩展性**  
  
    2.  **ASP.NET 2.0**  
  
    3.  **ISAPI 扩展**  
  
    4.  **ISAPI 筛选器**  
  
9. 在项标记为**World Wide Web 服务**，展开**常见 Http 功能**。  
  
10. 请确保**静态内容**选择。  
  
11. 在项标记为**World Wide Web 服务**，展开**安全**。  
  
12. 请确保**Windows 身份验证**选择。  
  
13. 下**Internet Information Services**目录中，展开项标记为**Web 管理工具**，然后选择**IIS 管理控制台**。  
  
14. 展开项标记为**IIS 6 管理兼容性**，然后选择**IIS 6 脚本工具**。  
  
15. 下**Internet Information Services**目录中，展开项标记为**Microsoft.NET Framework 3.5.1**，然后选择**Windows Communication Foundation Http 激活**.  
  
16. 单击“确定”。  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a>在 Windows Server 2008 上安装 IIS 7.0 版  
  
1.  从**服务器管理器**，选择**角色**。 下**角色摘要**，单击**添加角色**。  
  
2.  单击**下一步**以显示**选择服务器角色**对话框。  
  
3.  选择**应用程序服务器**从**角色**列表，，然后单击**下一步**两次以显示**选择角色服务**对话框应用程序服务器角色。  
  
4.  选择**Web 服务器 (IIS)**复选框。 如果系统提示你安装其他角色服务和功能，请单击**添加必需的功能**。 单击**下一步**两次以显示**选择角色服务**为 Web 服务器 (IIS) 角色的对话框。  
  
5.  展开**管理工具**，然后展开**IIS 6 管理兼容性**。 选择**IIS 6 脚本工具**。 如果系统提示你安装其他角色服务和功能，请单击**添加必需的角色服务**。 单击 **“下一步”**。  
  
6.  如果选项摘要正确无误，请单击**安装**。  
  
7.  当安装完成后时，单击**关闭**。  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a>在 Windows Vista 上安装 IIS 7.0 版  
  
1.  单击“开始”，然后单击“控制面板”。  
  
2.  选择**程序**组。  
  
3.  下**程序和功能**，单击**打开或关闭 Windows 功能**。  
  
4.  **用户帐户控制**显示对话框。 单击 **“继续”**。  
  
5.  **Windows 功能**显示对话框。 展开项标记为**Internet Information Services**。  
  
6.  展开项标记为**World Wide Web 服务**。  
  
7.  展开项标记为**应用程序开发功能**。  
  
8.  请确保以下各项处于选中状态：  
  
    1.  **.NET 扩展性**  
  
    2.  **ASP.NET 2.0**  
  
    3.  **ISAPI 扩展**  
  
    4.  **ISAPI 筛选器**  
  
9. 展开项标记为**Web 管理工具**，然后选择**IIS 管理控制台**。  
  
10. 在项标记为**World Wide Web 服务**，展开**常见 Http 功能**。  
  
11. 请确保**静态内容**选择。  
  
12. 在项标记为**World Wide Web 服务**，展开**安全**。  
  
13. 请确保**Windows 身份验证**选择。  
  
14. 展开项标记为**IIS 6 管理兼容性**，然后选择**IIS 6 脚本工具**。  
  
15. 展开项标记为**Microsoft.NET Framework 3.0**，然后选择**Windows Communication Foundation Http 激活**。  
  
16. 单击**确定**。  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a>在 Windows Server 2003 上安装 IIS 6.0 版  
  
1.  从**管理您的服务器**，单击**添加或删除角色**，然后单击**下一步**。  
  
2.  选择**应用程序服务器 （IIS，ASP.NET）**从**服务器角色**列表，，然后单击**下一步**。  
  
3.  选择**启用 ASP.NET**复选框，并依次**下一步**。  
  
4.  如果选项摘要正确无误，请单击“下一步”。  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a>在装有 Service Pack 2 和 Service Pack 3 的 Windows XP 上安装 IIS 5.1 版  
  
1.  在 Control Panel 中，单击**添加或删除程序**。  
  
2.  在**添加或删除程序**对话框中，单击**添加/删除 Windows 组件**。  
  
3.  在**Windows 组件向导**，选择**Internet 信息服务 (IIS)**复选框，并依次**下一步**。  
  
4.  如果**所需的文件**显示对话框中，插入操作系统的安装光盘，浏览至 i386 文件夹，然后单击**确定**。  
  
5.  当安装完成后时，单击**完成**。  
  
6.  关闭**添加或删除程序**对话框，然后再关闭**控制面板**。  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a>检验 IIS 和 ASP.NET 的安装  
  
1.  将本主题末尾的 HTML 文件保存到 \InetPub\wwwroot 根目录中并将其命名为 Default.aspx。  
  
2.  打开一个浏览器窗口。  
  
3.  类型`http://localhost/Default.aspx`中地址框中，然后按 enter 键。  
  
4.  应当会出现一个包含“Hello World”文本的网页。  
  
> [!NOTE]
>  每次安装新版本的 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 时，都必须将 aspnet_isapi 重新注册为 IIS 的 Web 服务扩展。 为此，发出 `aspnet_regiis –I –enable` 命令。  
  
## <a name="sample-code"></a>代码示例  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
