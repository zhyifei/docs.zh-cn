---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59980429"
---
# <a name="peertransportbindingelement"></a><span data-ttu-id="a075d-102">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="a075d-102">PeerTransportBindingElement</span></span>
<span data-ttu-id="a075d-103">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="a075d-103">PeerTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a075d-104">语法</span><span class="sxs-lookup"><span data-stu-id="a075d-104">Syntax</span></span>  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a075d-105">方法</span><span class="sxs-lookup"><span data-stu-id="a075d-105">Methods</span></span>  
 <span data-ttu-id="a075d-106">PeerTransportBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="a075d-106">The PeerTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a075d-107">属性</span><span class="sxs-lookup"><span data-stu-id="a075d-107">Properties</span></span>  
 <span data-ttu-id="a075d-108">PeerTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="a075d-108">The PeerTransportBindingElement class has the following properties:</span></span>  
  
### <a name="listenipaddress"></a><span data-ttu-id="a075d-109">ListenIPAddress</span><span class="sxs-lookup"><span data-stu-id="a075d-109">ListenIPAddress</span></span>  
 <span data-ttu-id="a075d-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="a075d-110">Data type: string</span></span>  
  
 <span data-ttu-id="a075d-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a075d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a075d-112">对等节点在其上侦听消息的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a075d-112">The IP address on which the peer node listens for messages.</span></span>  
  
### <a name="port"></a><span data-ttu-id="a075d-113">端口</span><span class="sxs-lookup"><span data-stu-id="a075d-113">Port</span></span>  
 <span data-ttu-id="a075d-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="a075d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="a075d-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a075d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a075d-116">网络接口端口，此绑定在该端口上处理对等通道消息。</span><span class="sxs-lookup"><span data-stu-id="a075d-116">The network interface port on which this binding processes peer channel messages.</span></span>  
  
### <a name="security"></a><span data-ttu-id="a075d-117">安全性</span><span class="sxs-lookup"><span data-stu-id="a075d-117">Security</span></span>  
 <span data-ttu-id="a075d-118">数据类型：PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="a075d-118">Data type: PeerSecuritySettings</span></span>  
  
 <span data-ttu-id="a075d-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a075d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a075d-120">对等传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="a075d-120">Peer transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a075d-121">要求</span><span class="sxs-lookup"><span data-stu-id="a075d-121">Requirements</span></span>  
  
|<span data-ttu-id="a075d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a075d-122">MOF</span></span>|<span data-ttu-id="a075d-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="a075d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a075d-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="a075d-124">Namespace</span></span>|<span data-ttu-id="a075d-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="a075d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a075d-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a075d-126">See also</span></span>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
