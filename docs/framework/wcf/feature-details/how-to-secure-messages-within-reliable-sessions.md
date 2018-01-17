---
title: "如何：在可靠会话内保护消息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 254cc241edf2d1c53ce9dd14eee41cd8bf6eaa76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>如何：在可靠会话内保护消息

本主题概述了使用系统提供的绑定之一来启用在可靠会话内交换的消息的消息级安全所需的步骤。这些绑定支持这种会话，但默认情况下不支持。 使用代码以强制方式或配置文件中以声明方式，请启用安全的可靠会话。 此过程使用客户端和服务配置文件来启用安全的可靠会话。

此过程由以下三个关键任务组成：

1. 指定客户端和服务在可靠会话内交换消息。

1. 在可靠会话内要求消息级安全。

1. 指定客户端必须用来向服务进行身份验证的客户端凭据类型。

务必在第一个终结点配置元素包含的任务中`bindingConfiguration`引用 （在本示例中） 名为的绑定配置的属性`MessageSecurity`。 [ **\<绑定 >** ](../../../../docs/framework/misc/binding.md)配置元素然后引用此名称来启用可靠会话通过设置`enabled`属性[  **\<reliableSession >** ](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)元素`true`。 通过将 `ordered` 属性设置为 `true`，可以要求可靠会话内的有序传送保证。

此配置过程所基于的示例源副本，请参阅[WS 可靠会话](../../../../docs/framework/wcf/samples/ws-reliable-session.md)。

第二个任务的重要项通过设置来完成`mode`属性**\<安全 >**中包含的元素**\<绑定 >**元素的客户端和服务`Message`。

第三个任务的重要项通过设置来完成`clientCredentialType`属性**\<消息 >**中包含的元素**\<安全 >**元素的客户端和服务`Certificate`。

> [!NOTE]
> 当使用可靠会话的消息安全，可靠消息传递尝试进行的未经身份验证的客户端身份验证直到发生超时，而不是引发异常后第一次失败。

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>使用 WSHttpBinding 以使用可靠会话配置服务

中介绍了此过程[How to: Exchange 消息在可靠会话](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)。

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>使用 WSHttpBinding 以使用可靠会话配置客户端

中介绍了此过程[How to: Exchange 消息在可靠会话](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)。

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>在配置中设置 mode 和 ClientCredentialType

1. 添加到合适的绑定元素[ **\<绑定 >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)配置文件元素。 下面的示例添加[  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)元素。

1. 添加**\<绑定 >**元素，并设置其`name`属性设为适当的值。 该示例使用名称`MessageSecurity`。

1. 添加**\<安全 >**元素，并设置`mode`属性设为`Message`。

1. 在**\<安全 >**元素中，添加**\<消息 >**元素，并设置`clientCredentialType`属性设为`Certificate`。

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
