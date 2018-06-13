---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: e64f689923d95546c8cecdf47c247faf79242ebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485750"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="fc3ec-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fc3ec-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="fc3ec-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fc3ec-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc3ec-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc3ec-104">Syntax</span></span>  
  
```  
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fc3ec-105">方法</span><span class="sxs-lookup"><span data-stu-id="fc3ec-105">Methods</span></span>  
 <span data-ttu-id="fc3ec-106">TcpTransportBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fc3ec-107">属性</span><span class="sxs-lookup"><span data-stu-id="fc3ec-107">Properties</span></span>  
 <span data-ttu-id="fc3ec-108">TcpTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="fc3ec-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="fc3ec-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fc3ec-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="fc3ec-110">数据类型：TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="fc3ec-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="fc3ec-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="fc3ec-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc3ec-112">连接池设置。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="fc3ec-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="fc3ec-113">ListenBacklog</span></span>  
 <span data-ttu-id="fc3ec-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="fc3ec-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="fc3ec-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="fc3ec-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc3ec-116">可挂起的最大排队连接请求数。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="fc3ec-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="fc3ec-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="fc3ec-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="fc3ec-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="fc3ec-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="fc3ec-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc3ec-120">一个布尔值，指定是否为此连接启用 TCP 端口共享。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="fc3ec-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="fc3ec-121">TeredoEnabled</span></span>  
 <span data-ttu-id="fc3ec-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="fc3ec-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="fc3ec-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="fc3ec-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fc3ec-124">一个布尔值，指定是否启用 Teredo（一种用于对防火墙后的客户端进行寻址的技术）。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc3ec-125">要求</span><span class="sxs-lookup"><span data-stu-id="fc3ec-125">Requirements</span></span>  
  
|<span data-ttu-id="fc3ec-126">MOF</span><span class="sxs-lookup"><span data-stu-id="fc3ec-126">MOF</span></span>|<span data-ttu-id="fc3ec-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fc3ec-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="fc3ec-128">Namespace</span></span>|<span data-ttu-id="fc3ec-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="fc3ec-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc3ec-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc3ec-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
