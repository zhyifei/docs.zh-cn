---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abaacfb6541d41019a8d0cd6df53913c6b7911f2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="onewaybindingelement"></a><span data-ttu-id="b0f89-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="b0f89-102">OneWayBindingElement</span></span>
<span data-ttu-id="b0f89-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="b0f89-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0f89-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0f89-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b0f89-105">方法</span><span class="sxs-lookup"><span data-stu-id="b0f89-105">Methods</span></span>  
 <span data-ttu-id="b0f89-106">OneWayBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b0f89-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b0f89-107">属性</span><span class="sxs-lookup"><span data-stu-id="b0f89-107">Properties</span></span>  
 <span data-ttu-id="b0f89-108">OneWayBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0f89-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="b0f89-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b0f89-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="b0f89-110">数据类型：ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b0f89-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="b0f89-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0f89-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0f89-112">通道池设置。</span><span class="sxs-lookup"><span data-stu-id="b0f89-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="b0f89-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="b0f89-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="b0f89-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b0f89-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0f89-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0f89-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0f89-116">接受的最大通道数。</span><span class="sxs-lookup"><span data-stu-id="b0f89-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="b0f89-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="b0f89-117">PacketRoutable</span></span>  
 <span data-ttu-id="b0f89-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b0f89-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b0f89-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0f89-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0f89-120">一个值，该值指示数据包是否可路由。</span><span class="sxs-lookup"><span data-stu-id="b0f89-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0f89-121">要求</span><span class="sxs-lookup"><span data-stu-id="b0f89-121">Requirements</span></span>  
  
|<span data-ttu-id="b0f89-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b0f89-122">MOF</span></span>|<span data-ttu-id="b0f89-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b0f89-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b0f89-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="b0f89-124">Namespace</span></span>|<span data-ttu-id="b0f89-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b0f89-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0f89-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0f89-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
