---
title: "Channel 类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93632d6a178c0f58143fc148a0e1eb51be94ed17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="channel-class"></a><span data-ttu-id="9ea2f-102">Channel 类</span><span class="sxs-lookup"><span data-stu-id="9ea2f-102">Channel class</span></span>
<span data-ttu-id="9ea2f-103">通道</span><span class="sxs-lookup"><span data-stu-id="9ea2f-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea2f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ea2f-104">Syntax</span></span>  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9ea2f-105">方法</span><span class="sxs-lookup"><span data-stu-id="9ea2f-105">Methods</span></span>  
 <span data-ttu-id="9ea2f-106">Channel 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="9ea2f-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9ea2f-107">属性</span><span class="sxs-lookup"><span data-stu-id="9ea2f-107">Properties</span></span>  
 <span data-ttu-id="9ea2f-108">Channel 类具有以下属性。</span><span class="sxs-lookup"><span data-stu-id="9ea2f-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="9ea2f-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="9ea2f-109">LocalAddress</span></span>  
 <span data-ttu-id="9ea2f-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9ea2f-110">Data type: string</span></span>  
  
 <span data-ttu-id="9ea2f-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9ea2f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ea2f-112">通道的本地终结点。</span><span class="sxs-lookup"><span data-stu-id="9ea2f-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9ea2f-113">ref</span><span class="sxs-lookup"><span data-stu-id="9ea2f-113">ref</span></span>  
 <span data-ttu-id="9ea2f-114">数据类型：Endpoint</span><span class="sxs-lookup"><span data-stu-id="9ea2f-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="9ea2f-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9ea2f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ea2f-116">对通道所连接到的终结点的引用。</span><span class="sxs-lookup"><span data-stu-id="9ea2f-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="9ea2f-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="9ea2f-117">RemoteAddress</span></span>  
 <span data-ttu-id="9ea2f-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9ea2f-118">Data type: string</span></span>  
  
 <span data-ttu-id="9ea2f-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9ea2f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ea2f-120">与通道相关联的远程地址。</span><span class="sxs-lookup"><span data-stu-id="9ea2f-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="9ea2f-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="9ea2f-121">SessionId</span></span>  
 <span data-ttu-id="9ea2f-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9ea2f-122">Data type: string</span></span>  
  
 <span data-ttu-id="9ea2f-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9ea2f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ea2f-124">当前会话的 ID（如果有）。</span><span class="sxs-lookup"><span data-stu-id="9ea2f-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="9ea2f-125">类型</span><span class="sxs-lookup"><span data-stu-id="9ea2f-125">Type</span></span>  
 <span data-ttu-id="9ea2f-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="9ea2f-126">Data type: string</span></span>  
  
 <span data-ttu-id="9ea2f-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9ea2f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ea2f-128">通道的类型。</span><span class="sxs-lookup"><span data-stu-id="9ea2f-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea2f-129">要求</span><span class="sxs-lookup"><span data-stu-id="9ea2f-129">Requirements</span></span>  
  
|<span data-ttu-id="9ea2f-130">MOF</span><span class="sxs-lookup"><span data-stu-id="9ea2f-130">MOF</span></span>|<span data-ttu-id="9ea2f-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="9ea2f-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9ea2f-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="9ea2f-132">Namespace</span></span>|<span data-ttu-id="9ea2f-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="9ea2f-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ea2f-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ea2f-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
