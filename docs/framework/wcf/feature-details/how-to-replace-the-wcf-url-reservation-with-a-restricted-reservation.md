---
title: "如何：用受限保留项替换 WCF URL 保留项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c25403f298444732f6787979add595bd877bb2c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>如何：用受限保留项替换 WCF URL 保留项
URL 保留项使您能够限制谁可以接收来自某个 URL 或某一组 URL 的消息。 保留项由一个 URL 模板、一个访问控制列表 (ACL) 和一组标志组成。 URL 模板定义保留项所影响的 URL。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]如何处理 URL 模板的更多信息，请参阅[路由传入请求](http://go.microsoft.com/fwlink/?LinkId=136764)。 ACL 控制哪个用户或用户组允许接收来自指定 URL 的消息。 标志指示保留项是赋予用户或用户组直接侦听 URL 的权限，还是将侦听权限委托给其他进程。  
  
 在默认的操作系统配置中，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 为端口 80 创建可全局访问的保留项，使所有用户都能够运行应用程序，在该应用程序中使用双向 HTTP 绑定来进行双工通信。 由于此保留项的 ACL 适用于所有用户，因此管理员不能显式允许或禁止侦听某个 URL 或某一组 URL 的权限。 本主题介绍如何删除此保留项，以及如何重新创建具有受限 ACL 的保留项。  
  
 在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 或 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上键入 `netsh http show urlacl`，就可以在具有提升权限的命令提示符中查看所有 HTTP URL 保留项。  下面的示例演示 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 保留项的形式。  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 该保留项包含的 URL 模板在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序使用 HTTP 双向绑定进行双工通信时使用。 这种 URL 由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务用于在通过 HTTP 双向绑定进行通信时将消息发送回 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端。 向每个用户授予侦听该 URL 的权限，而不将侦听权限委托给另一个进程。 最后，安全描述符定义语言 (SSDL) 中介绍了该 ACL。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]SSDL，请参阅[SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)  
  
### <a name="to-delete-the-wcf-url-reservation"></a>删除 WCF URL 保留项  
  
1.  单击**启动**，指向**所有程序**，单击**附件**，右键单击**命令提示符**单击**以运行管理员**上出现上下文菜单。 单击**继续**上用户帐户控制 (UAC) 窗口请求您权限才能继续。  
  
2.  键入**netsh http 删除 urlacl url = http: / / +:80/Temporary_Listen_Addresses/**在命令提示符窗口。  
  
3.  如果成功删除了保留项，将显示以下消息。 **已成功删除的 URL 保留项**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>创建新的安全组和新的受限 URL 保留项  
 若要用受限保留项替换 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 保留项，必须先创建新的安全组。 可以通过两种方法执行此操作：从命令提示符或从计算机管理控制台。 您只需要执行一次。  
  
#### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>从命令提示符创建新的安全组  
  
1.  单击**启动**，指向**所有程序**，单击**附件**，右键单击**命令提示符**单击**以运行管理员**上出现上下文菜单。 单击**继续**上用户帐户控制 (UAC) 窗口请求您权限才能继续。  
  
2.  键入**net localgroup"\<安全组名称 >"/ 注释:"\<安全组的说明 >"添加 /**在命令提示符。 替换**\<安全组名称 >**替换为你想要创建的安全组的名称和**\<安全组的说明 >**与具有合适的说明安全组。  
  
3.  如果成功创建了安全组，将显示以下消息。 **已成功完成该命令。**  
  
#### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>从计算机管理控制台创建新的安全组  
  
1.  单击**启动**，单击**控制面板**，单击**管理工具**，然后单击**计算机管理**以打开计算机管理控制台。 单击**继续**上用户帐户控制 (UAC) 窗口请求您权限才能继续。  
  
2.  单击**系统工具**，单击**本地用户和组**，右键单击**组**文件夹，然后单击**新建组**上下文菜单上，出现。 所需的类型**组名称**，**说明**和其他详细信息的该新的安全组并单击**创建**按钮创建安全组。  
  
#### <a name="to-create-the-restricted-url-reservation"></a>创建受限 URL 保留项  
  
1.  单击**启动**，指向**所有程序**，单击**附件**，右键单击**命令提示符**单击**以运行管理员**上出现上下文菜单。 单击**继续**上用户帐户控制 (UAC) 窗口请求您权限才能继续。  
  
2.  键入**netsh http 添加 urlacl url = http: / / +: 80/Temporary_Listen_Addresses/用户 ="\<计算机名称 >\\< 安全组名称\>**在命令提示符。 替换**\<计算机名称 >**与必须在其创建组的计算机名称和**\<安全组名称 >**替换为你创建的安全组的名称以前。  
  
3.  如果成功创建了保留项，将显示以下消息。 **已成功添加的 URL 保留项**。
