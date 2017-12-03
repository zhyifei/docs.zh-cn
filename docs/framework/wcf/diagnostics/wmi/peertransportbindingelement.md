---
title: PeerTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 193000acf2f3c8a0eddb2552559ee40a0f5fced9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="ada06-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ada06-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="ada06-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ada06-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ada06-104">语法</span><span class="sxs-lookup"><span data-stu-id="ada06-104">Syntax</span></span>  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ada06-105">方法</span><span class="sxs-lookup"><span data-stu-id="ada06-105">Methods</span></span>  
 <span data-ttu-id="ada06-106">PeerTransportBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="ada06-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ada06-107">属性</span><span class="sxs-lookup"><span data-stu-id="ada06-107">Properties</span></span>  
 <span data-ttu-id="ada06-108">PeerTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="ada06-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="ada06-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="ada06-109">ListenIPAddress</span></span>  
 <span data-ttu-id="ada06-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ada06-110">Data type: string</span></span>  
  
 <span data-ttu-id="ada06-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ada06-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ada06-112">对等节点在其上侦听消息的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ada06-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="ada06-113">端口</span><span class="sxs-lookup"><span data-stu-id="ada06-113">Port</span></span>  
 <span data-ttu-id="ada06-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="ada06-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="ada06-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ada06-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ada06-116">网络接口端口，此绑定在该端口上处理对等通道消息。</span><span class="sxs-lookup"><span data-stu-id="ada06-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="ada06-117">安全性</span><span class="sxs-lookup"><span data-stu-id="ada06-117">Security</span></span>  
 <span data-ttu-id="ada06-118">数据类型：PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ada06-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="ada06-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ada06-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ada06-120">对等传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="ada06-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ada06-121">要求</span><span class="sxs-lookup"><span data-stu-id="ada06-121">Requirements</span></span>  
  
|<span data-ttu-id="ada06-122">MOF</span><span class="sxs-lookup"><span data-stu-id="ada06-122">MOF</span></span>|<span data-ttu-id="ada06-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ada06-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ada06-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="ada06-124">Namespace</span></span>|<span data-ttu-id="ada06-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ada06-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ada06-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ada06-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
