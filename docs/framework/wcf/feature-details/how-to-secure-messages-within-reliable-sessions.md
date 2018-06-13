---
title: 如何：在可靠会话内保护消息
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4c320d74f7e7966bfa35c824dbe30da768cd1447
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493238"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="fe834-102">如何：在可靠会话内保护消息</span><span class="sxs-lookup"><span data-stu-id="fe834-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="fe834-103">本主题概述了使用系统提供的绑定之一来启用在可靠会话内交换的消息的消息级安全所需的步骤。这些绑定支持这种会话，但默认情况下不支持。</span><span class="sxs-lookup"><span data-stu-id="fe834-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="fe834-104">使用代码以强制方式或配置文件中以声明方式，请启用安全的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="fe834-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="fe834-105">此过程使用客户端和服务配置文件来启用安全的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="fe834-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="fe834-106">此过程由以下三个关键任务组成：</span><span class="sxs-lookup"><span data-stu-id="fe834-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="fe834-107">指定客户端和服务在可靠会话内交换消息。</span><span class="sxs-lookup"><span data-stu-id="fe834-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="fe834-108">在可靠会话内要求消息级安全。</span><span class="sxs-lookup"><span data-stu-id="fe834-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="fe834-109">指定客户端必须用来向服务进行身份验证的客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="fe834-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="fe834-110">务必在第一个终结点配置元素包含的任务中`bindingConfiguration`引用 （在本示例中） 名为的绑定配置的属性`MessageSecurity`。</span><span class="sxs-lookup"><span data-stu-id="fe834-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="fe834-111">[ **\<绑定 >** ](../../../../docs/framework/misc/binding.md)配置元素然后引用此名称来启用可靠会话通过设置`enabled`属性[  **\<reliableSession >** ](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)元素`true`。</span><span class="sxs-lookup"><span data-stu-id="fe834-111">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="fe834-112">通过将 `ordered` 属性设置为 `true`，可以要求可靠会话内的有序传送保证。</span><span class="sxs-lookup"><span data-stu-id="fe834-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="fe834-113">此配置过程所基于的示例源副本，请参阅[WS 可靠会话](../../../../docs/framework/wcf/samples/ws-reliable-session.md)。</span><span class="sxs-lookup"><span data-stu-id="fe834-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="fe834-114">第二个任务的重要项通过设置来完成`mode`属性**\<安全 >** 中包含的元素**\<绑定 >** 元素的客户端和服务`Message`。</span><span class="sxs-lookup"><span data-stu-id="fe834-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="fe834-115">第三个任务的重要项通过设置来完成`clientCredentialType`属性**\<消息 >** 中包含的元素**\<安全 >** 元素的客户端和服务`Certificate`。</span><span class="sxs-lookup"><span data-stu-id="fe834-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="fe834-116">当使用可靠会话的消息安全，可靠消息传递尝试进行的未经身份验证的客户端身份验证直到发生超时，而不是引发异常后第一次失败。</span><span class="sxs-lookup"><span data-stu-id="fe834-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="fe834-117">使用 WSHttpBinding 以使用可靠会话配置服务</span><span class="sxs-lookup"><span data-stu-id="fe834-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="fe834-118">中介绍了此过程[How to: Exchange 消息在可靠会话](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)。</span><span class="sxs-lookup"><span data-stu-id="fe834-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="fe834-119">使用 WSHttpBinding 以使用可靠会话配置客户端</span><span class="sxs-lookup"><span data-stu-id="fe834-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="fe834-120">中介绍了此过程[How to: Exchange 消息在可靠会话](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)。</span><span class="sxs-lookup"><span data-stu-id="fe834-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="fe834-121">在配置中设置 mode 和 ClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="fe834-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="fe834-122">添加到合适的绑定元素[ **\<绑定 >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)配置文件元素。</span><span class="sxs-lookup"><span data-stu-id="fe834-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="fe834-123">下面的示例添加[  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="fe834-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="fe834-124">添加**\<绑定 >** 元素，并设置其`name`属性设为适当的值。</span><span class="sxs-lookup"><span data-stu-id="fe834-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="fe834-125">该示例使用名称`MessageSecurity`。</span><span class="sxs-lookup"><span data-stu-id="fe834-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="fe834-126">添加**\<安全 >** 元素，并设置`mode`属性设为`Message`。</span><span class="sxs-lookup"><span data-stu-id="fe834-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="fe834-127">在**\<安全 >** 元素中，添加**\<消息 >** 元素，并设置`clientCredentialType`属性设为`Certificate`。</span><span class="sxs-lookup"><span data-stu-id="fe834-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
