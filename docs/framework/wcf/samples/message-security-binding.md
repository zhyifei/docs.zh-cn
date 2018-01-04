---
title: "消息安全绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4570ce7-864e-461b-85d8-0f7bcc53c2c8
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f0c8b125d3fc313dca4140b871ccea8165329fda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-binding"></a><span data-ttu-id="9daec-102">消息安全绑定</span><span class="sxs-lookup"><span data-stu-id="9daec-102">Message Security Binding</span></span>
<span data-ttu-id="9daec-103">本节包含演示 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的 Windows 服务中消息安全绑定的示例。</span><span class="sxs-lookup"><span data-stu-id="9daec-103">This section contains samples that demonstrate message security binding in Windows Services in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9daec-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="9daec-104">In This Section</span></span>  
 [<span data-ttu-id="9daec-105">匿名消息安全</span><span class="sxs-lookup"><span data-stu-id="9daec-105">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 <span data-ttu-id="9daec-106">此示例演示如何实现 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 应用程序，该应用程序使用不带客户端身份验证的消息级安全性，但需要使用服务器的 X.509 证书进行服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="9daec-106">This sample demonstrates how to implement a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application that uses message-level security with no client authentication but that requires server authentication using the server's X.509 certificate.</span></span>  
  
 [<span data-ttu-id="9daec-107">消息安全证书</span><span class="sxs-lookup"><span data-stu-id="9daec-107">Message Security Certificate</span></span>](../../../../docs/framework/wcf/samples/message-security-certificate.md)  
 <span data-ttu-id="9daec-108">此示例演示如何实现一个应用程序，该应用程序对客户端使用 WS 安全性和 X.509 v3 证书身份验证，并要求使用服务器的 X.509 v3 证书进行服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="9daec-108">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span>  
  
 [<span data-ttu-id="9daec-109">用户名消息安全</span><span class="sxs-lookup"><span data-stu-id="9daec-109">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 <span data-ttu-id="9daec-110">本示例演示如何实现一个应用程序，该应用程序对客户端使用具有用户名身份验证的 WS-Security，并要求使用服务器的 X.509v3 证书对服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9daec-110">This sample demonstrates how to implement an application that uses WS-Security with username authentication for the client and requires server authentication using the server's X.509v3 certificate.</span></span>  
  
 [<span data-ttu-id="9daec-111">Windows 消息安全</span><span class="sxs-lookup"><span data-stu-id="9daec-111">Message Security Windows</span></span>](../../../../docs/framework/wcf/samples/message-security-windows.md)  
 <span data-ttu-id="9daec-112">本示例演示如何将 <xref:System.ServiceModel.WSHttpBinding> 绑定配置为使用具有 Windows 身份验证的消息级安全性。</span><span class="sxs-lookup"><span data-stu-id="9daec-112">This sample demonstrates how to configure a <xref:System.ServiceModel.WSHttpBinding> binding to use message-level security with Windows authentication.</span></span>
