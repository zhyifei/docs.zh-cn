---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6d2717bc2d1d14e369af2b9c5a8c0affb67501d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124223"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="e0ec4-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e0ec4-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="e0ec4-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="e0ec4-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ec4-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0ec4-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e0ec4-105">方法</span><span class="sxs-lookup"><span data-stu-id="e0ec4-105">Methods</span></span>  
 <span data-ttu-id="e0ec4-106">TcpTransportBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="e0ec4-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e0ec4-107">属性</span><span class="sxs-lookup"><span data-stu-id="e0ec4-107">Properties</span></span>  
 <span data-ttu-id="e0ec4-108">TcpTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="e0ec4-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="e0ec4-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e0ec4-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="e0ec4-110">数据类型：TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="e0ec4-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="e0ec4-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e0ec4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0ec4-112">连接池设置。</span><span class="sxs-lookup"><span data-stu-id="e0ec4-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="e0ec4-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="e0ec4-113">ListenBacklog</span></span>  
 <span data-ttu-id="e0ec4-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="e0ec4-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="e0ec4-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e0ec4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0ec4-116">可挂起的最大排队连接请求数。</span><span class="sxs-lookup"><span data-stu-id="e0ec4-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="e0ec4-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="e0ec4-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="e0ec4-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="e0ec4-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="e0ec4-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e0ec4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0ec4-120">一个布尔值，指定是否为此连接启用 TCP 端口共享。</span><span class="sxs-lookup"><span data-stu-id="e0ec4-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="e0ec4-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="e0ec4-121">TeredoEnabled</span></span>  
 <span data-ttu-id="e0ec4-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="e0ec4-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="e0ec4-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e0ec4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0ec4-124">一个布尔值，指定是否启用 Teredo（一种用于对防火墙后的客户端进行寻址的技术）。</span><span class="sxs-lookup"><span data-stu-id="e0ec4-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ec4-125">要求</span><span class="sxs-lookup"><span data-stu-id="e0ec4-125">Requirements</span></span>  
  
|<span data-ttu-id="e0ec4-126">MOF</span><span class="sxs-lookup"><span data-stu-id="e0ec4-126">MOF</span></span>|<span data-ttu-id="e0ec4-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="e0ec4-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e0ec4-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="e0ec4-128">Namespace</span></span>|<span data-ttu-id="e0ec4-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="e0ec4-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0ec4-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0ec4-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
