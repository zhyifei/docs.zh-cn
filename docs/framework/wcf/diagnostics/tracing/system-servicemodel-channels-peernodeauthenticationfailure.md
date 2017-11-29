---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b09d7fc476d5eed7f7c534fdde46cb18eeac30d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="2d556-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="2d556-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="2d556-103">与潜在邻居的安全握手没有成功。</span><span class="sxs-lookup"><span data-stu-id="2d556-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2d556-104">描述</span><span class="sxs-lookup"><span data-stu-id="2d556-104">Description</span></span>  
 <span data-ttu-id="2d556-105">此跟踪在尝试建立安全邻居连接时发生。</span><span class="sxs-lookup"><span data-stu-id="2d556-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="2d556-106">凭据不充足或不正确可以导致出现此情况。</span><span class="sxs-lookup"><span data-stu-id="2d556-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="2d556-107">对等通道只能识别一种强标识令牌类型，即 X.509 证书，X.509 证书基于可实现的身份验证和授权类型，提供强标识模型。</span><span class="sxs-lookup"><span data-stu-id="2d556-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="2d556-108">对等通道还可通过使用密码为简单应用程序提供支持。</span><span class="sxs-lookup"><span data-stu-id="2d556-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="2d556-109">密码仅用于允许加入会话，不能用于执行消息身份验证。</span><span class="sxs-lookup"><span data-stu-id="2d556-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="2d556-110">这是因为对等端组共享的对称令牌难以、也不适合用于进行源身份验证。</span><span class="sxs-lookup"><span data-stu-id="2d556-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2d556-111">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2d556-111">Troubleshooting</span></span>  
 <span data-ttu-id="2d556-112">确保所有邻居都具有适当的安全凭据。</span><span class="sxs-lookup"><span data-stu-id="2d556-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d556-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d556-113">See Also</span></span>  
 [<span data-ttu-id="2d556-114">对等通道安全性</span><span class="sxs-lookup"><span data-stu-id="2d556-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [<span data-ttu-id="2d556-115">跟踪</span><span class="sxs-lookup"><span data-stu-id="2d556-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2d556-116">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="2d556-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2d556-117">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="2d556-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
