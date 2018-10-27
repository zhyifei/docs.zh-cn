---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 04326484bbf1f07c66ad8fb401642880f9ba8c6e
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2018
ms.locfileid: "50033709"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="b688d-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b688d-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="b688d-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b688d-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b688d-104">语法</span><span class="sxs-lookup"><span data-stu-id="b688d-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b688d-105">方法</span><span class="sxs-lookup"><span data-stu-id="b688d-105">Methods</span></span>  
 <span data-ttu-id="b688d-106">TcpTransportBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b688d-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b688d-107">属性</span><span class="sxs-lookup"><span data-stu-id="b688d-107">Properties</span></span>  
 <span data-ttu-id="b688d-108">TcpTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="b688d-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="b688d-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b688d-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="b688d-110">数据类型：TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b688d-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="b688d-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b688d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b688d-112">连接池设置。</span><span class="sxs-lookup"><span data-stu-id="b688d-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="b688d-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="b688d-113">ListenBacklog</span></span>  
 <span data-ttu-id="b688d-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b688d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b688d-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b688d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b688d-116">可挂起的最大排队连接请求数。</span><span class="sxs-lookup"><span data-stu-id="b688d-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="b688d-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="b688d-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="b688d-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b688d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b688d-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b688d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b688d-120">一个布尔值，指定是否为此连接启用 TCP 端口共享。</span><span class="sxs-lookup"><span data-stu-id="b688d-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="b688d-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="b688d-121">TeredoEnabled</span></span>  
 <span data-ttu-id="b688d-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b688d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b688d-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b688d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b688d-124">一个布尔值，指定是否启用 Teredo（一种用于对防火墙后的客户端进行寻址的技术）。</span><span class="sxs-lookup"><span data-stu-id="b688d-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b688d-125">要求</span><span class="sxs-lookup"><span data-stu-id="b688d-125">Requirements</span></span>  
  
|<span data-ttu-id="b688d-126">MOF</span><span class="sxs-lookup"><span data-stu-id="b688d-126">MOF</span></span>|<span data-ttu-id="b688d-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b688d-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b688d-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="b688d-128">Namespace</span></span>|<span data-ttu-id="b688d-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b688d-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b688d-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="b688d-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
