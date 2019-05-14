---
title: 对等协作
ms.date: 03/30/2017
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
ms.openlocfilehash: 0c257782ad391bb8de61caffdd13af1f2872ef6c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623173"
---
# <a name="peer-to-peer-collaboration"></a><span data-ttu-id="2c208-102">对等协作</span><span class="sxs-lookup"><span data-stu-id="2c208-102">Peer-to-peer collaboration</span></span>

<span data-ttu-id="2c208-103">对等网络服务利用存在于 Internet 边缘的相对强大的计算机（个人计算机）完成各项任务，不仅仅是基于客户端的计算任务。</span><span class="sxs-lookup"><span data-stu-id="2c208-103">Peer-to-peer networking is the utilization of the relatively powerful computers (personal computers) that exist at the edge of the Internet for more than just client-based computing tasks.</span></span> <span data-ttu-id="2c208-104">现代个人电脑 (PC) 具有超快处理器、大量存储和大型硬盘，在执行电子邮件和 Web 浏览等常见计算任务时，并未充分利用这些优势。</span><span class="sxs-lookup"><span data-stu-id="2c208-104">The modern personal computer (PC) has a very fast processor, vast memory, and a large hard disk, none of which are being fully utilized when performing common computing tasks such as email and Web browsing.</span></span> <span data-ttu-id="2c208-105">现代 PC 可以轻松地充当许多类型的应用程序的客户端和服务器（对等机）。</span><span class="sxs-lookup"><span data-stu-id="2c208-105">The modern PC can easily act as both a client and server (a peer) for many types of applications.</span></span>  
  
<span data-ttu-id="2c208-106">对等协作基础架构是 Microsoft Windows 对等基础架构的简化实现，它利用了 Windows Vista 及更高版本平台中的网络邻居服务。</span><span class="sxs-lookup"><span data-stu-id="2c208-106">The Peer-to-Peer Collaboration Infrastructure is a simplified implementation of the Microsoft Windows Peer-to-Peer Infrastructure that leverages the People Near Me service in Windows Vista and later platforms.</span></span> <span data-ttu-id="2c208-107">它最适用于网络邻居服务运行的子网内启用了对等的应用程序，尽管它也可为 Internet 终结点或联系人提供服务。</span><span class="sxs-lookup"><span data-stu-id="2c208-107">It is best used for peer-enabled applications within a subnet for which the People Near Me service operates, although it can service internet endpoints or contacts as well.</span></span> <span data-ttu-id="2c208-108">它集成了 Live Messenger 和其他 Live 感知应用程序使用的常见联系人管理器，以确定联系人终结点、可用性和状态。</span><span class="sxs-lookup"><span data-stu-id="2c208-108">It incorporates the common Contact Manager that is used by Live Messenger and other Live-aware applications to determine contact endpoints, availability, and presence.</span></span>  
  
## <a name="collaboration-applications"></a><span data-ttu-id="2c208-109">协作应用程序</span><span class="sxs-lookup"><span data-stu-id="2c208-109">Collaboration applications</span></span>

 <span data-ttu-id="2c208-110">典型的对等协作应用程序包含以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2c208-110">A typical peer-to-peer collaboration application is comprised of the following steps:</span></span>  
  
- <span data-ttu-id="2c208-111">对等机确定有兴趣托管协作会话的对等机身份</span><span class="sxs-lookup"><span data-stu-id="2c208-111">Peer determines the identity of a peer who is interested in hosting a collaboration session</span></span>  
  
- <span data-ttu-id="2c208-112">以某种方式发送托管会话请求，主机对等机同意管理协作活动。</span><span class="sxs-lookup"><span data-stu-id="2c208-112">A request to host a session is sent, somehow, and the host peer agrees to manage collaboration activity.</span></span>  
  
- <span data-ttu-id="2c208-113">主机邀请子网联系人（包括请求者）参与会话。</span><span class="sxs-lookup"><span data-stu-id="2c208-113">The host invites contacts on the subnet (including the requestor) to a session.</span></span>  
  
- <span data-ttu-id="2c208-114">希望协作的所有对等机均可将主机添加到其联系人管理器。</span><span class="sxs-lookup"><span data-stu-id="2c208-114">All peers who want to collaborate may add the host to their contact managers.</span></span>  
  
- <span data-ttu-id="2c208-115">无论接受还是拒绝，大多数对等机将及时向主机对等机发回邀请回复。</span><span class="sxs-lookup"><span data-stu-id="2c208-115">Most peers will send invitation responses, whether accepted or declined, back to the host peer in a timely fashion.</span></span>  
  
- <span data-ttu-id="2c208-116">所有希望协作的对等机都将订阅主机对等机。</span><span class="sxs-lookup"><span data-stu-id="2c208-116">All peers who want to collaborate will subscribe to the host peer.</span></span>  
  
- <span data-ttu-id="2c208-117">当对等机正在执行其初始协作活动时，主机对等机可向其联系人管理器添加远程对等机。</span><span class="sxs-lookup"><span data-stu-id="2c208-117">While the peers are performing their initial collaboration activity, the host peer may add remote peers to its contact manager.</span></span> <span data-ttu-id="2c208-118">它还处理所有邀请回复，以确定接受者、拒绝者、未答复者。</span><span class="sxs-lookup"><span data-stu-id="2c208-118">It also processes all invitation responses to determine who has accepted, who has declined, and who has not answered.</span></span>  <span data-ttu-id="2c208-119">它可能会取消邀请那些尚未答复或执行一些其他活动的人。</span><span class="sxs-lookup"><span data-stu-id="2c208-119">It may cancel invitations to those who have not answered, or perform some other activity.</span></span>  
  
- <span data-ttu-id="2c208-120">此时，主机对等机可与所有受邀对等机开始协作会话，或向协作基础架构注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c208-120">At this point, the host peer can start a collaboration session with all invited peers, or register an application with the collaboration infrastructure.</span></span>  <span data-ttu-id="2c208-121">P2P 应用程序使用对等协作基础架构和 <xref:System.Net.PeerToPeer.Collaboration> 命名空间来协调游戏、公告牌、会议和其他无服务器状态应用程序的通信。</span><span class="sxs-lookup"><span data-stu-id="2c208-121">P2P applications use the Peer-to-Peer Collaboration Infrastructure and the <xref:System.Net.PeerToPeer.Collaboration> namespace to coordinate communications for games, bulletin boards, conferencing, and other serverless presence applications.</span></span>  
  
## <a name="peer-to-peer-networking-security"></a><span data-ttu-id="2c208-122">对等网络安全</span><span class="sxs-lookup"><span data-stu-id="2c208-122">Peer-to-peer networking security</span></span>  

 <span data-ttu-id="2c208-123">在 Active Directory 域中，域控制器使用 Kerberos 提供身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="2c208-123">In an Active Directory domain, domain controllers provide authentication services using Kerberos.</span></span> <span data-ttu-id="2c208-124">在无服务器对等环境中，对等机必须提供其自身的身份验证。</span><span class="sxs-lookup"><span data-stu-id="2c208-124">In a serverless peer environment, the peers must provide their own authentication.</span></span> <span data-ttu-id="2c208-125">对于对等网络，任何节点都可充当 CA，无需要求每个对等机受信任根存储中存在根证书。</span><span class="sxs-lookup"><span data-stu-id="2c208-125">For Peer-to-Peer Networking, any node can act as a CA, removing the requirement of a root certificate in each peer's trusted root store.</span></span> <span data-ttu-id="2c208-126">使用自签名证书提供身份验证，格式为 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="2c208-126">Authentication is provided using self-signed certificates, formatted as X.509 certificates.</span></span> <span data-ttu-id="2c208-127">这些是由每个对等机创建的证书，其生成公钥/私钥对以及使用私钥签名的证书。</span><span class="sxs-lookup"><span data-stu-id="2c208-127">These are certificates that are created by each peer, which generates the public key/private key pair and the certificate that is signed using the private key.</span></span> <span data-ttu-id="2c208-128">自签名证书用于身份验证，并提供有关对等机实体的信息。</span><span class="sxs-lookup"><span data-stu-id="2c208-128">The self-signed certificate is used for authentication and to provide information about the peer entity.</span></span> <span data-ttu-id="2c208-129">如 X.509 身份验证一样，对等机网络身份验证依赖于一系列追溯受信任公钥的证书。</span><span class="sxs-lookup"><span data-stu-id="2c208-129">Like X.509 authentication, peer networking authentication relies upon a chain of certificates tracing back to a public key that is trusted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c208-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c208-130">See also</span></span>

- <xref:System.Net.PeerToPeer.Collaboration>
- [<span data-ttu-id="2c208-131">关于 System.Net.PeerToPeer.Collaboration 命名空间</span><span class="sxs-lookup"><span data-stu-id="2c208-131">About the System.Net.PeerToPeer.Collaboration Namespace</span></span>](../../../docs/framework/network-programming/about-the-system-net-peertopeer-collaboration-namespace.md)
