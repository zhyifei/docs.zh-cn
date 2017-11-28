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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1df634a61cce695fca74fdfe53beea6c0f83d082
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="channel-class"></a><span data-ttu-id="721dd-102">Channel 类</span><span class="sxs-lookup"><span data-stu-id="721dd-102">Channel class</span></span>
<span data-ttu-id="721dd-103">通道</span><span class="sxs-lookup"><span data-stu-id="721dd-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="721dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="721dd-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="721dd-105">方法</span><span class="sxs-lookup"><span data-stu-id="721dd-105">Methods</span></span>  
 <span data-ttu-id="721dd-106">Channel 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="721dd-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="721dd-107">属性</span><span class="sxs-lookup"><span data-stu-id="721dd-107">Properties</span></span>  
 <span data-ttu-id="721dd-108">Channel 类具有以下属性。</span><span class="sxs-lookup"><span data-stu-id="721dd-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="721dd-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="721dd-109">LocalAddress</span></span>  
 <span data-ttu-id="721dd-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="721dd-110">Data type: string</span></span>  
  
 <span data-ttu-id="721dd-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="721dd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="721dd-112">通道的本地终结点。</span><span class="sxs-lookup"><span data-stu-id="721dd-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="721dd-113">ref</span><span class="sxs-lookup"><span data-stu-id="721dd-113">ref</span></span>  
 <span data-ttu-id="721dd-114">数据类型：Endpoint</span><span class="sxs-lookup"><span data-stu-id="721dd-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="721dd-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="721dd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="721dd-116">对通道所连接到的终结点的引用。</span><span class="sxs-lookup"><span data-stu-id="721dd-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="721dd-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="721dd-117">RemoteAddress</span></span>  
 <span data-ttu-id="721dd-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="721dd-118">Data type: string</span></span>  
  
 <span data-ttu-id="721dd-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="721dd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="721dd-120">与通道相关联的远程地址。</span><span class="sxs-lookup"><span data-stu-id="721dd-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="721dd-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="721dd-121">SessionId</span></span>  
 <span data-ttu-id="721dd-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="721dd-122">Data type: string</span></span>  
  
 <span data-ttu-id="721dd-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="721dd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="721dd-124">当前会话的 ID（如果有）。</span><span class="sxs-lookup"><span data-stu-id="721dd-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="721dd-125">类型</span><span class="sxs-lookup"><span data-stu-id="721dd-125">Type</span></span>  
 <span data-ttu-id="721dd-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="721dd-126">Data type: string</span></span>  
  
 <span data-ttu-id="721dd-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="721dd-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="721dd-128">通道的类型。</span><span class="sxs-lookup"><span data-stu-id="721dd-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="721dd-129">要求</span><span class="sxs-lookup"><span data-stu-id="721dd-129">Requirements</span></span>  
  
|<span data-ttu-id="721dd-130">MOF</span><span class="sxs-lookup"><span data-stu-id="721dd-130">MOF</span></span>|<span data-ttu-id="721dd-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="721dd-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="721dd-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="721dd-132">Namespace</span></span>|<span data-ttu-id="721dd-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="721dd-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="721dd-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="721dd-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
