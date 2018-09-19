---
title: 如何：用受限预留替换 WCF URL 预留
ms.date: 03/30/2017
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
ms.openlocfilehash: b53596d7ac4e7e7c3748f6a98130492a96c0b48c
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46288339"
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>如何：用受限预留替换 WCF URL 预留
URL 预留使你能够限制谁可以接收来自某个 URL 或某一组 URL 的消息。 预留由一个 URL 模板、一个访问控制列表 (ACL) 和一组标志组成。 URL 模板定义预留所影响的 URL。 有关如何处理 URL 模板的详细信息，请参阅[路由传入的请求](https://go.microsoft.com/fwlink/?LinkId=136764)。 ACL 控制哪个用户或用户组允许接收来自指定 URL 的消息。 标志指示预留是赋予用户或用户组直接侦听 URL 的权限，还是将侦听权限委托给其他进程。  
  
 作为默认操作系统配置的一部分，Windows Communication Foundation (WCF) 创建可全局访问保留端口 80，若要启用所有用户运行的双工通信中使用双向 HTTP 绑定的应用程序。 由于此预留的 ACL 适用于所有用户，因此管理员不能显式允许或禁止侦听某个 URL 或某一组 URL 的权限。 本主题介绍如何删除此预留，以及如何重新创建具有受限 ACL 的预留。  
  
 在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 或 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上键入 `netsh http show urlacl`，就可以在具有提升权限的命令提示符中查看所有 HTTP URL 预留。  下面的示例演示 WCF URL 保留项应类似于。  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 该保留项包含在 WCF 应用程序使用 HTTP 双向绑定进行双工通信时使用的 URL 模板。 此窗体的 Url 的 WCF 服务中用于消息发送回 WCF 客户端时通过 HTTP 双向绑定进行通信。 向每个用户授予侦听该 URL 的权限，而不将侦听权限委托给另一个进程。 最后，安全描述符定义语言 (SSDL) 中介绍了该 ACL。 SSDL 的更多信息，请参阅[SSDL](https://go.microsoft.com/fwlink/?LinkId=136789)  
  
### <a name="to-delete-the-wcf-url-reservation"></a>删除 WCF URL 预留  
  
1.  单击**启动**，指向**所有程序**，单击**附件**，右键单击**命令提示符下**单击**以运行管理员**上出现的上下文菜单。 单击**继续**上可能会要求权限才能继续运行的用户帐户控制 (UAC) 窗口。  
  
2.  在键入**netsh http delete urlacl =http://+:80/Temporary_Listen_Addresses/** 在命令提示符窗口中。  
  
3.  如果成功删除了预留，将显示以下消息。 **已成功删除 URL 保留项**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>创建新的安全组和新的受限 URL 预留  
 若要用受限保留项替换 WCF URL 保留项必须首先创建新的安全组。 可以通过两种方法执行此操作：从命令提示符或从计算机管理控制台。 您只需要执行一次。  
  
#### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>从命令提示符创建新的安全组  
  
1.  单击**启动**，指向**所有程序**，单击**附件**，右键单击**命令提示符下**单击**以运行管理员**上出现的上下文菜单。 单击**继续**上可能会要求权限才能继续运行的用户帐户控制 (UAC) 窗口。  
  
2.  在键入**net localgroup"\<安全组名称 >"/ 注释:"\<安全组说明 >"/add**在命令提示符下。 替换**\<安全组名称 >** 具有你想要创建的安全组的名称和**\<安全组说明 >** 替换为适当的说明安全组。  
  
3.  如果成功创建了安全组，将显示以下消息。 **命令已成功完成。**  
  
#### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>从计算机管理控制台创建新的安全组  
  
1.  单击**启动**，单击**控制面板**，单击**管理工具**，然后单击**计算机管理**开启计算机管理控制台。 单击**继续**上可能会要求权限才能继续运行的用户帐户控制 (UAC) 窗口。  
  
2.  单击**系统工具**，单击**本地用户和组**，右键单击**组**文件夹，然后单击**新建组**上下文菜单上的出现。 中的所需的类型**组名称**，**说明**和其他详细信息的该新的安全组并单击**创建**按钮以创建安全组。  
  
#### <a name="to-create-the-restricted-url-reservation"></a>创建受限 URL 预留  
  
1.  单击**启动**，指向**所有程序**，单击**附件**，右键单击**命令提示符下**单击**以运行管理员**上出现的上下文菜单。 单击**继续**上可能会要求权限才能继续运行的用户帐户控制 (UAC) 窗口。  
  
2.  在键入**netsh http add urlacl =http://+:80/Temporary_Listen_Addresses/用户 ="\<计算机名称 >\\< 安全组名称\>** 在命令提示符处。 替换**\<计算机名称 >** 使用的计算机名称必须在其创建组并**\<安全组名称 >** 具有您创建的安全组的名称以前。  
  
3.  如果成功创建了预留，将显示以下消息。 **已成功添加 URL 保留项**。
