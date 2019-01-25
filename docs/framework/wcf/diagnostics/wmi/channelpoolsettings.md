---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 4a3e45140765f99f4a30b77fc9d02b167601b50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591468"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="e8482-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e8482-102">ChannelPoolSettings</span></span>
<span data-ttu-id="e8482-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e8482-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8482-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8482-104">Syntax</span></span>  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e8482-105">方法</span><span class="sxs-lookup"><span data-stu-id="e8482-105">Methods</span></span>  
 <span data-ttu-id="e8482-106">ChannelPoolSettings 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="e8482-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e8482-107">属性</span><span class="sxs-lookup"><span data-stu-id="e8482-107">Properties</span></span>  
 <span data-ttu-id="e8482-108">ChannelPoolSettings 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="e8482-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="e8482-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="e8482-109">IdleTimeout</span></span>  
 <span data-ttu-id="e8482-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="e8482-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="e8482-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e8482-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8482-112">连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="e8482-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="e8482-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="e8482-113">LeaseTimeout</span></span>  
 <span data-ttu-id="e8482-114">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="e8482-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="e8482-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e8482-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8482-116">超时前完成租约操作的最大时间。</span><span class="sxs-lookup"><span data-stu-id="e8482-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="e8482-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e8482-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="e8482-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="e8482-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="e8482-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e8482-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8482-120">每个终结点的最大出站通道数。</span><span class="sxs-lookup"><span data-stu-id="e8482-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8482-121">要求</span><span class="sxs-lookup"><span data-stu-id="e8482-121">Requirements</span></span>  
  
|<span data-ttu-id="e8482-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e8482-122">MOF</span></span>|<span data-ttu-id="e8482-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="e8482-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e8482-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="e8482-124">Namespace</span></span>|<span data-ttu-id="e8482-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="e8482-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8482-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8482-126">See also</span></span>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
