---
title: TcpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e230cbccee211fbda219000fbbd2cda5275776b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="95572-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="95572-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="95572-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="95572-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95572-104">语法</span><span class="sxs-lookup"><span data-stu-id="95572-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="95572-105">方法</span><span class="sxs-lookup"><span data-stu-id="95572-105">Methods</span></span>  
 <span data-ttu-id="95572-106">TcpTransportBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="95572-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="95572-107">属性</span><span class="sxs-lookup"><span data-stu-id="95572-107">Properties</span></span>  
 <span data-ttu-id="95572-108">TcpTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="95572-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="95572-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="95572-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="95572-110">数据类型：TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="95572-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="95572-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="95572-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95572-112">连接池设置。</span><span class="sxs-lookup"><span data-stu-id="95572-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="95572-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="95572-113">ListenBacklog</span></span>  
 <span data-ttu-id="95572-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="95572-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="95572-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="95572-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95572-116">可挂起的最大排队连接请求数。</span><span class="sxs-lookup"><span data-stu-id="95572-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="95572-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="95572-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="95572-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="95572-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="95572-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="95572-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95572-120">一个布尔值，指定是否为此连接启用 TCP 端口共享。</span><span class="sxs-lookup"><span data-stu-id="95572-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="95572-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="95572-121">TeredoEnabled</span></span>  
 <span data-ttu-id="95572-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="95572-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="95572-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="95572-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="95572-124">一个布尔值，指定是否启用 Teredo（一种用于对防火墙后的客户端进行寻址的技术）。</span><span class="sxs-lookup"><span data-stu-id="95572-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95572-125">惠?</span><span class="sxs-lookup"><span data-stu-id="95572-125">Requirements</span></span>  
  
|<span data-ttu-id="95572-126">MOF</span><span class="sxs-lookup"><span data-stu-id="95572-126">MOF</span></span>|<span data-ttu-id="95572-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="95572-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="95572-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="95572-128">Namespace</span></span>|<span data-ttu-id="95572-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="95572-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95572-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="95572-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
