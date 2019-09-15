---
title: 如何：用受限预留替换 WCF URL 预留
ms.date: 03/30/2017
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
ms.openlocfilehash: 981c4890b11130b937e176da78f378340c0d3894
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991666"
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>如何：用受限预留替换 WCF URL 预留
URL 预留使你能够限制谁可以接收来自某个 URL 或某一组 URL 的消息。 预留由一个 URL 模板、一个访问控制列表 (ACL) 和一组标志组成。 URL 模板定义预留所影响的 URL。 有关如何处理 URL 模板的详细信息，请参阅[路由传入的请求](https://go.microsoft.com/fwlink/?LinkId=136764)。 ACL 控制哪个用户或用户组允许接收来自指定 URL 的消息。 标志指示预留是赋予用户或用户组直接侦听 URL 的权限，还是将侦听权限委托给其他进程。  
  
 作为默认操作系统配置的一部分，Windows Communication Foundation （WCF）为端口80创建一个全局可访问的保留项，以使所有用户都能运行使用双 HTTP 绑定进行双工通信的应用程序。 由于此预留的 ACL 适用于所有用户，因此管理员不能显式允许或禁止侦听某个 URL 或某一组 URL 的权限。 本主题介绍如何删除此预留，以及如何重新创建具有受限 ACL 的预留。  
  
 在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 或 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上键入 `netsh http show urlacl`，就可以在具有提升权限的命令提示符中查看所有 HTTP URL 预留。  下面的示例演示 WCF URL 保留项应类似的内容。  

```
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```

 当 WCF 应用程序使用 HTTP 双重绑定进行双工通信时，预订由使用的 URL 模板组成。 当通过 HTTP 双重绑定进行通信时，此窗体的 Url 用于 WCF 服务，以将消息发送回 WCF 客户端。 向每个用户授予侦听该 URL 的权限，而不将侦听权限委托给另一个进程。 最后，安全描述符定义语言 (SSDL) 中介绍了该 ACL。 有关 SSDL 的详细信息，请参阅[ssdl](https://go.microsoft.com/fwlink/?LinkId=136789)  
  
## <a name="to-delete-the-wcf-url-reservation"></a>删除 WCF URL 预留  
  
1. 单击 "**开始**"，指向 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后在出现的上下文菜单中单击 "**以管理员身份运行**"。 在可能会要求权限继续的用户帐户控制（UAC）窗口上单击 "**继续**"。  
  
2. 在命令提示符窗口中键入**netsh http http://+:80/Temporary_Listen_Addresses/ delete urlacl url =** 。  
  
3. 如果成功删除了预留，将显示以下消息。 **已成功删除 URL 保留项**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>创建新的安全组和新的受限 URL 预留  
 若要用受限保留项替换 WCF URL 保留项，您必须首先创建一个新的安全组。 可以通过两种方法执行此操作：从命令提示符或从计算机管理控制台。 您只需要执行一次。  
  
### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>从命令提示符创建新的安全组  
  
1. 单击 "**开始**"，指向 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后在出现的上下文菜单中单击 "**以管理员身份运行**"。 在可能会要求权限继续的用户帐户控制（UAC）窗口上单击 "**继续**"。  
  
2. 在命令提示符下键入**net localgroup "\<安全组名称 >"\</comment： "安全组描述 >"/add** 。 将 **\<安全组名称 >** 替换为要创建的安全组的名称，并将安全组描述替换为安全组 **\<说明 >** ，并为安全组提供适当的说明。  
  
3. 如果成功创建了安全组，将显示以下消息。 **命令已成功完成。**  
  
### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>从计算机管理控制台创建新的安全组  
  
1. 依次单击 "**开始**"、 **"控制面板**"、"**管理工具**"，然后单击 "**计算机管理**" 以打开 "计算机管理" 控制台。 在可能会要求权限继续的用户帐户控制（UAC）窗口上单击 "**继续**"。  
  
2. 单击 "**系统工具**"，单击 "**本地用户和组**"，右键单击 "**组**" 文件夹，然后在出现的上下文菜单上单击 "**新建组**"。 键入此新安全组所需的**组名称**、**说明**和其他详细信息，然后单击 "**创建**" 按钮创建安全组。  
  
### <a name="to-create-the-restricted-url-reservation"></a>创建受限 URL 预留  
  
1. 单击 "**开始**"，指向 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后在出现的上下文菜单中单击 "**以管理员身份运行**"。 在可能会要求权限继续的用户帐户控制（UAC）窗口上单击 "**继续**"。  
  
2. 在命令提示符下键入**netsh http add http://+:80/Temporary_Listen_Addresses/ urlacl url =\< user = "\\ 计算机名称 > <\> 安全组名称**。 将 **\<计算机名称 >** 替换为必须在其上创建组的计算机名称，并 **\<将安全组名称 >** 为之前创建的安全组的名称。  
  
3. 如果成功创建了预留，将显示以下消息。 **已成功添加 URL 保留**项。
