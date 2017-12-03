---
title: TcpConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eaec1b7d179810faaba016cfa0c5eb7e6c950ab6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="tcpconnectionpoolsettings"></a><span data-ttu-id="99669-102">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="99669-102">TcpConnectionPoolSettings</span></span>
<span data-ttu-id="99669-103">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="99669-103">TcpConnectionPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99669-104">语法</span><span class="sxs-lookup"><span data-stu-id="99669-104">Syntax</span></span>  
  
```  
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="99669-105">方法</span><span class="sxs-lookup"><span data-stu-id="99669-105">Methods</span></span>  
 <span data-ttu-id="99669-106">TcpConnectionPoolSettings 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="99669-106">The TcpConnectionPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="99669-107">属性</span><span class="sxs-lookup"><span data-stu-id="99669-107">Properties</span></span>  
 <span data-ttu-id="99669-108">TcpConnectionPoolSettings 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="99669-108">The TcpConnectionPoolSettings class has the following properties:</span></span>  
  
### <a name="groupname"></a><span data-ttu-id="99669-109">GroupName</span><span class="sxs-lookup"><span data-stu-id="99669-109">GroupName</span></span>  
 <span data-ttu-id="99669-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="99669-110">Data type: string</span></span>  
  
 <span data-ttu-id="99669-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="99669-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99669-112">绑定元素使用的连接池的组名。</span><span class="sxs-lookup"><span data-stu-id="99669-112">The group name of the connection pool used by the binding element.</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="99669-113">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="99669-113">IdleTimeout</span></span>  
 <span data-ttu-id="99669-114">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="99669-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="99669-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="99669-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99669-116">连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="99669-116">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="99669-117">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="99669-117">LeaseTimeout</span></span>  
 <span data-ttu-id="99669-118">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="99669-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="99669-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="99669-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99669-120">超时前完成租约操作的最大时间。</span><span class="sxs-lookup"><span data-stu-id="99669-120">The maximum time for the lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundconnectionsperendpoint"></a><span data-ttu-id="99669-121">MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="99669-121">MaxOutboundConnectionsPerEndpoint</span></span>  
 <span data-ttu-id="99669-122">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="99669-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="99669-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="99669-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99669-124">每个终结点的最大出站连接数。</span><span class="sxs-lookup"><span data-stu-id="99669-124">The maximum outbound connections for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99669-125">要求</span><span class="sxs-lookup"><span data-stu-id="99669-125">Requirements</span></span>  
  
|<span data-ttu-id="99669-126">MOF</span><span class="sxs-lookup"><span data-stu-id="99669-126">MOF</span></span>|<span data-ttu-id="99669-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="99669-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="99669-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="99669-128">Namespace</span></span>|<span data-ttu-id="99669-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="99669-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99669-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99669-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
