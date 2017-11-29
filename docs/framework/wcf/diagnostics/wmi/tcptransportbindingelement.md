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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 180e954661319cb32edfd3180418fe9b1571ea5c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="5ea8c-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5ea8c-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="5ea8c-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="5ea8c-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ea8c-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ea8c-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5ea8c-105">方法</span><span class="sxs-lookup"><span data-stu-id="5ea8c-105">Methods</span></span>  
 <span data-ttu-id="5ea8c-106">TcpTransportBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="5ea8c-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5ea8c-107">属性</span><span class="sxs-lookup"><span data-stu-id="5ea8c-107">Properties</span></span>  
 <span data-ttu-id="5ea8c-108">TcpTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="5ea8c-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="5ea8c-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5ea8c-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="5ea8c-110">数据类型：TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5ea8c-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="5ea8c-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5ea8c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5ea8c-112">连接池设置。</span><span class="sxs-lookup"><span data-stu-id="5ea8c-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="5ea8c-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="5ea8c-113">ListenBacklog</span></span>  
 <span data-ttu-id="5ea8c-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="5ea8c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="5ea8c-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5ea8c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5ea8c-116">可挂起的最大排队连接请求数。</span><span class="sxs-lookup"><span data-stu-id="5ea8c-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="5ea8c-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="5ea8c-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="5ea8c-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="5ea8c-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="5ea8c-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5ea8c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5ea8c-120">一个布尔值，指定是否为此连接启用 TCP 端口共享。</span><span class="sxs-lookup"><span data-stu-id="5ea8c-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="5ea8c-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="5ea8c-121">TeredoEnabled</span></span>  
 <span data-ttu-id="5ea8c-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="5ea8c-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="5ea8c-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5ea8c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5ea8c-124">一个布尔值，指定是否启用 Teredo（一种用于对防火墙后的客户端进行寻址的技术）。</span><span class="sxs-lookup"><span data-stu-id="5ea8c-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ea8c-125">要求</span><span class="sxs-lookup"><span data-stu-id="5ea8c-125">Requirements</span></span>  
  
|<span data-ttu-id="5ea8c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="5ea8c-126">MOF</span></span>|<span data-ttu-id="5ea8c-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="5ea8c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5ea8c-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="5ea8c-128">Namespace</span></span>|<span data-ttu-id="5ea8c-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="5ea8c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ea8c-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ea8c-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
