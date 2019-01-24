---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 437ccc0446e3cc05596ab12b7908177b7f78e431
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670649"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="e5e1c-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e5e1c-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="e5e1c-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e5e1c-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5e1c-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e5e1c-105">方法</span><span class="sxs-lookup"><span data-stu-id="e5e1c-105">Methods</span></span>  
 <span data-ttu-id="e5e1c-106">PeerTransportBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="e5e1c-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e5e1c-107">Properties</span><span class="sxs-lookup"><span data-stu-id="e5e1c-107">Properties</span></span>  
 <span data-ttu-id="e5e1c-108">PeerTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="e5e1c-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="e5e1c-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="e5e1c-109">ListenIPAddress</span></span>  
 <span data-ttu-id="e5e1c-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e5e1c-110">Data type: string</span></span>  
  
 <span data-ttu-id="e5e1c-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e5e1c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5e1c-112">对等节点在其上侦听消息的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e5e1c-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="e5e1c-113">端口</span><span class="sxs-lookup"><span data-stu-id="e5e1c-113">Port</span></span>  
 <span data-ttu-id="e5e1c-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="e5e1c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="e5e1c-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e5e1c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5e1c-116">网络接口端口，此绑定在该端口上处理对等通道消息。</span><span class="sxs-lookup"><span data-stu-id="e5e1c-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="e5e1c-117">安全性</span><span class="sxs-lookup"><span data-stu-id="e5e1c-117">Security</span></span>  
 <span data-ttu-id="e5e1c-118">数据类型：PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="e5e1c-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="e5e1c-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e5e1c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e5e1c-120">对等传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="e5e1c-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5e1c-121">要求</span><span class="sxs-lookup"><span data-stu-id="e5e1c-121">Requirements</span></span>  
  
|<span data-ttu-id="e5e1c-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e5e1c-122">MOF</span></span>|<span data-ttu-id="e5e1c-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="e5e1c-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e5e1c-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="e5e1c-124">Namespace</span></span>|<span data-ttu-id="e5e1c-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="e5e1c-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5e1c-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5e1c-126">See also</span></span>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
