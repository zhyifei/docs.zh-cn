---
title: ChannelPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e97e934673efbc6d0f72751c7cb1de6fba84a141
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="068d6-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="068d6-102">ChannelPoolSettings</span></span>
<span data-ttu-id="068d6-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="068d6-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="068d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="068d6-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="068d6-105">方法</span><span class="sxs-lookup"><span data-stu-id="068d6-105">Methods</span></span>  
 <span data-ttu-id="068d6-106">ChannelPoolSettings 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="068d6-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="068d6-107">属性</span><span class="sxs-lookup"><span data-stu-id="068d6-107">Properties</span></span>  
 <span data-ttu-id="068d6-108">ChannelPoolSettings 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="068d6-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="068d6-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="068d6-109">IdleTimeout</span></span>  
 <span data-ttu-id="068d6-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="068d6-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="068d6-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="068d6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="068d6-112">连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="068d6-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="068d6-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="068d6-113">LeaseTimeout</span></span>  
 <span data-ttu-id="068d6-114">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="068d6-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="068d6-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="068d6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="068d6-116">超时前完成租约操作的最大时间。</span><span class="sxs-lookup"><span data-stu-id="068d6-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="068d6-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="068d6-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="068d6-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="068d6-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="068d6-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="068d6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="068d6-120">每个终结点的最大出站通道数。</span><span class="sxs-lookup"><span data-stu-id="068d6-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="068d6-121">要求</span><span class="sxs-lookup"><span data-stu-id="068d6-121">Requirements</span></span>  
  
|<span data-ttu-id="068d6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="068d6-122">MOF</span></span>|<span data-ttu-id="068d6-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="068d6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="068d6-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="068d6-124">Namespace</span></span>|<span data-ttu-id="068d6-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="068d6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="068d6-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="068d6-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
