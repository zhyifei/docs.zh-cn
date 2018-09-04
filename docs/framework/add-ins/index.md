---
title: 外接程序和扩展性
ms.date: 03/30/2017
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb2485f2ecf0426360dba80d443500a92b5a7af6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510049"
---
# <a name="add-ins-and-extensibility"></a>外接程序和扩展性
<a name="top"></a> 外接程序为主机应用程序提供扩展功能或服务。 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 提供了一个编程模型，开发人员可利用此模型来开发外接程序并在其主机应用程序中激活。 该模型通过在主机与外接程序之间构造通信管道来实现此功能。 该模型通过使用 <xref:System.AddIn>、 <xref:System.AddIn.Hosting>、 <xref:System.AddIn.Pipeline>和 <xref:System.AddIn.Contract> 命名空间中的类实现。  
  
 本概述包含以下几节：  
  
-   [外接程序模型](#addin_model)  
  
-   [区分外接程序和主机](#distinguishing_between_addins_and_hosts)  
  
-   [相关主题](#related_topics)  
  
-   [引用](#reference)  
  
> [!NOTE]
>  您可以找到其他示例代码和客户工具技术预览生成外接程序管道，用于在[CodePlex 上的托管扩展性和外接程序框架网站](https://go.microsoft.com/fwlink/?LinkId=121190)。  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a>外接程序模型  
 外接程序模型包括组成外接程序管道（也称为通信管道）的一系列段，管道实现外接程序与主机之间的所有通信。 管道是使外接程序与主机实现数据交换的段的对称通信模型。 在主机与外接程序之间开发这些段可提供实现外接程序版本控制和隔离所需的抽象层。  
  
 下图显示外接程序管道。  
  
 ![添加&#45;管道模型中。](../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
外接程序管道  
  
 这些段的程序集不需要处于同一个应用程序域。 可以将外接程序加载至其自己的新应用程序域、现有应用程序域，甚至主机的应用程序域。 可以将多个外接程序加载到同一个应用程序域，这样外接程序便可以共享资源和安全性上下文。  
  
 外接程序模型支持并建议在主机与外接程序之间构建可选边界，即隔离边界（也称为远程边界）。 此边界可以是应用程序域边界或进程边界。  
  
 管道中间的合约段同时加载至主机的应用程序域和外接程序的应用程序域。 合约定义主机与外接程序用于互相交换类型的虚拟方式。  
  
 若要通过隔离边界，则必须是合约或可序列化类型。 非合约或非可序列化类型必须由管道中的适配器段转换为合约。  
  
 管道的视图段是抽象基类或接口，可为主机和外接程序提供它们共享的方式视图，如合约所定义。  
  
 有关开发管道段的详细信息，请参阅 [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)。  
  
 后面的部分介绍外接程序模型的功能。  
  
### <a name="independent-versioning"></a>独立版本控制  
 外接程序模型允许主机和外接程序独立进行版本控制。 正因如此，外接程序支持以下方案：  
  
-   创建适配器，使主机可以使用为旧主机版本生成的外接程序。  
  
-   创建适配器，使主机可以使用为新版本主机生成的外接程序。  
  
-   创建适配器，使主机可以使用为其他主机生成的外接程序。  
  
### <a name="discovery-and-activation"></a>发现和激活  
 可以使用表示从信息存储中找到的外接程序的集合中的令牌激活外接程序。 通过搜索定义主机的外接程序视图的类型找到外接程序。 还可以按定义外接程序的类型来查找特定的外接程序。 信息存储区包括两个缓存文件：管道存储区和外接程序存储区。  
  
 有关更新和重新生成的信息存储区的信息，请参阅[外接程序发现](https://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421)。 有关激活外接程序的信息，请参阅[外接程序激活](https://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f)并[如何： 激活外接程序具有不同的隔离和安全性](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5)。  
  
### <a name="isolation-levels-and-external-processes"></a>隔离级别和外部进程  
 外接程序模型在外接程序与其主机之间或者两个外接程序之间支持几个隔离级别。这些隔离级别如下所示（从低到高顺序）：  
  
-   外接程序在与主机相同的应用程序域中运行。 不建议这样做，因为这不具备隔离和卸载功能，而使用不同的应用程序域时则可以获得这些功能。  
  
-   多个外接程序加载到主机所使用应用程序域之外的同一应用程序域。  
  
-   每个外接程序以独占方式加载到自己的应用程序域。 这是最常见的隔离级别。  
  
-   多个外接程序在外部进程中加载到同一应用程序域。  
  
-   每个外接程序在外部进程中以独占方式加载到自己的应用程序域。 这是最高级别的隔离方案。  
  
 有关使用外部进程的详细信息，请参阅[如何： 激活外接程序具有不同的隔离和安全性](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5)。  
  
### <a name="lifetime-management"></a>生存期管理  
 由于外接程序模型跨应用程序域和进程边界，因此自身的垃圾回收不足以释放和回收对象。 外接程序模型提供一种生存期管理机制，该机制使用令牌和引用计数，并且通常不需要额外的编程。 有关详细信息，请参阅[生存期管理](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)。  
  
 [返回页首](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a>区分外接程序和主机  
 外接程序与主机的区别仅仅是主机能够激活外接程序。 主机可以是两个应用程序中较大的一个（如文字处理应用程序及其拼写检查器），也可以是两个应用程序中较小的一个（嵌入媒体播放中的即时消息客户端）。 外接程序模型支持客户端和服务器方案中的外接程序。 服务器外接程序的示例包括为电子邮件服务器提供病毒扫描、垃圾邮件过滤以及 IP 保护的外接程序。 客户端外接程序示例包括引用的插件文字处理器、 图形程序和游戏和病毒扫描的本地电子邮件客户端的特殊功能。  
  
 [返回页首](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)|描述从主机应用程序到外接程序之间的段的通信管道。 提供介绍如何构造管道以及如何将段部署到 Visual Studio 中的管道的演练主题中的代码示例。|  
|[应用程序域和程序集](https://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)|描述（为安全性、可靠性和版本控制提供隔离边界的）应用程序域与程序集之间的关系。|  
  
 [返回页首](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a>参考  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [返回页首](#top)