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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48364c2bcfa50476ac5f9f00f87c17f97dc14017
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="b0229-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b0229-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="b0229-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b0229-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0229-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0229-104">Syntax</span></span>  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b0229-105">方法</span><span class="sxs-lookup"><span data-stu-id="b0229-105">Methods</span></span>  
 <span data-ttu-id="b0229-106">PeerTransportBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b0229-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b0229-107">属性</span><span class="sxs-lookup"><span data-stu-id="b0229-107">Properties</span></span>  
 <span data-ttu-id="b0229-108">PeerTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0229-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="b0229-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="b0229-109">ListenIPAddress</span></span>  
 <span data-ttu-id="b0229-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b0229-110">Data type: string</span></span>  
  
 <span data-ttu-id="b0229-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0229-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0229-112">对等节点在其上侦听消息的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b0229-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="b0229-113">端口</span><span class="sxs-lookup"><span data-stu-id="b0229-113">Port</span></span>  
 <span data-ttu-id="b0229-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b0229-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0229-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0229-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0229-116">网络接口端口，此绑定在该端口上处理对等通道消息。</span><span class="sxs-lookup"><span data-stu-id="b0229-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="b0229-117">安全性</span><span class="sxs-lookup"><span data-stu-id="b0229-117">Security</span></span>  
 <span data-ttu-id="b0229-118">数据类型：PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="b0229-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="b0229-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0229-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0229-120">对等传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="b0229-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0229-121">要求</span><span class="sxs-lookup"><span data-stu-id="b0229-121">Requirements</span></span>  
  
|<span data-ttu-id="b0229-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b0229-122">MOF</span></span>|<span data-ttu-id="b0229-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b0229-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b0229-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="b0229-124">Namespace</span></span>|<span data-ttu-id="b0229-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b0229-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0229-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0229-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
