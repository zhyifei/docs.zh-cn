---
title: 关于 System.Net.PeerToPeer.Collaboration 命名空间
ms.date: 03/30/2017
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
ms.openlocfilehash: a62b659472f6d05e61672fa603e8663d9946977e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127902"
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a><span data-ttu-id="f93cd-102">关于 System.Net.PeerToPeer.Collaboration 命名空间</span><span class="sxs-lookup"><span data-stu-id="f93cd-102">About the System.Net.PeerToPeer.Collaboration Namespace</span></span>
<span data-ttu-id="f93cd-103"><xref:System.Net.PeerToPeer.Collaboration> 命名空间提供用于通过对等协作基础结构实现对等协作活动的类和 API。</span><span class="sxs-lookup"><span data-stu-id="f93cd-103">The <xref:System.Net.PeerToPeer.Collaboration> namespace provides classes and APIs that are used to implement peer collaboration activities using the Peer-to-Peer Collaboration Infrastructure.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="f93cd-104">类</span><span class="sxs-lookup"><span data-stu-id="f93cd-104">Classes</span></span>  
 <span data-ttu-id="f93cd-105">在对等协作活动的实现中所使用的主要类包括：</span><span class="sxs-lookup"><span data-stu-id="f93cd-105">The main classes used in the implementation of a Peer-to-Peer Collaboration activity are:</span></span>  
  
-   <span data-ttu-id="f93cd-106"><xref:System.Net.PeerToPeer.Collaboration.ContactManager>，可用于存储对等联系人。</span><span class="sxs-lookup"><span data-stu-id="f93cd-106">The <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, which can be used to store peer contacts.</span></span>  
  
-   <span data-ttu-id="f93cd-107"><xref:System.Net.PeerToPeer.Collaboration.PeerApplication>，可在其中进行协作，如游戏、聊天客户端或会议解决方案。</span><span class="sxs-lookup"><span data-stu-id="f93cd-107">The <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> in which to collaborate, such as a game, chat client, or conferencing solution.</span></span>  
  
-   <span data-ttu-id="f93cd-108">将在活动中进行协作的对等机。</span><span class="sxs-lookup"><span data-stu-id="f93cd-108">The peers that will be collaborating in an activity.</span></span>  <span data-ttu-id="f93cd-109">这些对等机可以表示为 <xref:System.Net.PeerToPeer.Collaboration.PeerContact>、<xref:System.Net.PeerToPeer.Collaboration.PeerNearMe> 或 <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> 对象。</span><span class="sxs-lookup"><span data-stu-id="f93cd-109">These peers can be represented as <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, or <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> objects.</span></span>  
  
-   <span data-ttu-id="f93cd-110"><xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> 静态类本身，用于指定可用的应用程序和参与其中的对等机。</span><span class="sxs-lookup"><span data-stu-id="f93cd-110">The static <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> class itself, which specifies which applications are available and which peers are participating in them.</span></span>  
  
 <span data-ttu-id="f93cd-111"><xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> 方法用于将对等机邀请至协作会话。</span><span class="sxs-lookup"><span data-stu-id="f93cd-111">The <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> methods are used to invite peers to a collaboration session.</span></span>  <span data-ttu-id="f93cd-112">针对向与协作会话关联的应用程序、对象或状态信息发送更新信号的事件，调用对等机可订阅另一个对等机。</span><span class="sxs-lookup"><span data-stu-id="f93cd-112">A calling peer can subscribe to another peer for events that signal updates to application, object, or presence information affiliated with the collaboration session.</span></span> <span data-ttu-id="f93cd-113">状态类指定 <xref:System.Net.PeerToPeer.Collaboration.Peer> 是否可用于协作，<xref:System.Net.PeerToPeer.Collaboration.PeerScope> 类用于指定对等机可允许的参与程度：<xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet>（全局）、<xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>（子网）或 <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>。</span><span class="sxs-lookup"><span data-stu-id="f93cd-113">Presence classes specify whether a <xref:System.Net.PeerToPeer.Collaboration.Peer> is available for collaboration, and the <xref:System.Net.PeerToPeer.Collaboration.PeerScope> class is used to specify how much participation is allowed for a peer:  <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (global), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (subnet) or <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.</span></span>  
  
 <span data-ttu-id="f93cd-114">协作会话由四个步骤组成：</span><span class="sxs-lookup"><span data-stu-id="f93cd-114">A collaboration session is comprised of four steps:</span></span>  
  
-   <span data-ttu-id="f93cd-115">发现。</span><span class="sxs-lookup"><span data-stu-id="f93cd-115">Discovery.</span></span> <span data-ttu-id="f93cd-116">发现或发布应用程序、对等机和状态信息。</span><span class="sxs-lookup"><span data-stu-id="f93cd-116">Discover or publish applications, peers, and presence information.</span></span>  <span data-ttu-id="f93cd-117">例如，在本地子网上查找安装了相同游戏的其他人。</span><span class="sxs-lookup"><span data-stu-id="f93cd-117">For instance, find other people on the local subnet that have the same games installed.</span></span>  
  
-   <span data-ttu-id="f93cd-118">邀请。</span><span class="sxs-lookup"><span data-stu-id="f93cd-118">Invitation.</span></span> <span data-ttu-id="f93cd-119">发送和接受远程对等机的安全邀请以启动或加入 <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> 会话。</span><span class="sxs-lookup"><span data-stu-id="f93cd-119">Send and accept secure invitations for remote peer(s) to start or join <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> sessions.</span></span>  
  
-   <span data-ttu-id="f93cd-120">联系人管理。</span><span class="sxs-lookup"><span data-stu-id="f93cd-120">Contact Management.</span></span> <span data-ttu-id="f93cd-121">将发现的对等机作为联系人添加到 <xref:System.Net.PeerToPeer.Collaboration.ContactManager>。</span><span class="sxs-lookup"><span data-stu-id="f93cd-121">Add discovered peers as a contact to a <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.</span></span>  
  
-   <span data-ttu-id="f93cd-122">通信。</span><span class="sxs-lookup"><span data-stu-id="f93cd-122">Communication.</span></span> <span data-ttu-id="f93cd-123">建立通信后，请使用 <xref:System.Net> API、<xref:System.Net.PeerToPeer> API 或 Windows Communication Foundation 对等通道类来进行多方通信。</span><span class="sxs-lookup"><span data-stu-id="f93cd-123">When communication is established, use the <xref:System.Net> APIs, the <xref:System.Net.PeerToPeer> API, or the Windows Communication Foundation Peer Channel classes for multiparty communications.</span></span>  
  
 <span data-ttu-id="f93cd-124">例如，主机对等机启动协作会话并利用 <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> 方法将远程对等机和其中一个本地对等机添加到主机对等机的联系人管理中。</span><span class="sxs-lookup"><span data-stu-id="f93cd-124">For example, the host peer starts a collaboration session, and utilizes the <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> method to add a remote peer and one of its local peers to the Contact Manager of the host peer.</span></span>  <span data-ttu-id="f93cd-125">这三位用户随后便可参与到他们自己的专用协作会话。</span><span class="sxs-lookup"><span data-stu-id="f93cd-125">The three users will then participate in their own private collaboration session.</span></span>  
  
 <span data-ttu-id="f93cd-126">典型的 P2P 应用程序包括：用于协作进行笔记或白板记录的电话会议、无服务器的聊天应用程序、交互式播发和联机游戏会话。</span><span class="sxs-lookup"><span data-stu-id="f93cd-126">Typical P2P applications are: conference calls for collaborative note-taking or whiteboarding, serverless chat applications, interactive advertisements, and online gaming sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f93cd-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="f93cd-127">See also</span></span>

- <xref:System.Net.PeerToPeer.Collaboration>
