---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 8900af77d0d385bb68b4b85e1d15be57bb7a8d14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963966"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="b0a80-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b0a80-102">ChannelPoolSettings</span></span>
<span data-ttu-id="b0a80-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b0a80-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a80-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0a80-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b0a80-105">方法</span><span class="sxs-lookup"><span data-stu-id="b0a80-105">Methods</span></span>  
 <span data-ttu-id="b0a80-106">ChannelPoolSettings 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b0a80-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b0a80-107">属性</span><span class="sxs-lookup"><span data-stu-id="b0a80-107">Properties</span></span>  
 <span data-ttu-id="b0a80-108">ChannelPoolSettings 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="b0a80-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="b0a80-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="b0a80-109">IdleTimeout</span></span>  
 <span data-ttu-id="b0a80-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="b0a80-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="b0a80-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0a80-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0a80-112">连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="b0a80-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="b0a80-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="b0a80-113">LeaseTimeout</span></span>  
 <span data-ttu-id="b0a80-114">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="b0a80-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="b0a80-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0a80-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0a80-116">超时前完成租约操作的最大时间。</span><span class="sxs-lookup"><span data-stu-id="b0a80-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="b0a80-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b0a80-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="b0a80-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b0a80-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0a80-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0a80-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0a80-120">每个终结点的最大出站通道数。</span><span class="sxs-lookup"><span data-stu-id="b0a80-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0a80-121">要求</span><span class="sxs-lookup"><span data-stu-id="b0a80-121">Requirements</span></span>  
  
|<span data-ttu-id="b0a80-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b0a80-122">MOF</span></span>|<span data-ttu-id="b0a80-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b0a80-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b0a80-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="b0a80-124">Namespace</span></span>|<span data-ttu-id="b0a80-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b0a80-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0a80-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0a80-126">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
