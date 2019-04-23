---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 6d2717bc2d1d14e369af2b9c5a8c0affb67501d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979233"
---
# <a name="tcptransportbindingelement"></a><span data-ttu-id="20374-102">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="20374-102">TcpTransportBindingElement</span></span>
<span data-ttu-id="20374-103">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="20374-103">TcpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20374-104">语法</span><span class="sxs-lookup"><span data-stu-id="20374-104">Syntax</span></span>  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="20374-105">方法</span><span class="sxs-lookup"><span data-stu-id="20374-105">Methods</span></span>  
 <span data-ttu-id="20374-106">TcpTransportBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="20374-106">The TcpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="20374-107">属性</span><span class="sxs-lookup"><span data-stu-id="20374-107">Properties</span></span>  
 <span data-ttu-id="20374-108">TcpTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="20374-108">The TcpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="connectionpoolsettings"></a><span data-ttu-id="20374-109">ConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="20374-109">ConnectionPoolSettings</span></span>  
 <span data-ttu-id="20374-110">数据类型：TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="20374-110">Data type: TcpConnectionPoolSettings</span></span>  
  
 <span data-ttu-id="20374-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="20374-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20374-112">连接池设置。</span><span class="sxs-lookup"><span data-stu-id="20374-112">The connection pool settings.</span></span>  
  
### <a name="listenbacklog"></a><span data-ttu-id="20374-113">ListenBacklog</span><span class="sxs-lookup"><span data-stu-id="20374-113">ListenBacklog</span></span>  
 <span data-ttu-id="20374-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="20374-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="20374-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="20374-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20374-116">可挂起的最大排队连接请求数。</span><span class="sxs-lookup"><span data-stu-id="20374-116">The maximum number of queued connection requests that can be pending.</span></span>  
  
### <a name="portsharingenabled"></a><span data-ttu-id="20374-117">PortSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="20374-117">PortSharingEnabled</span></span>  
 <span data-ttu-id="20374-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="20374-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="20374-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="20374-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20374-120">一个布尔值，指定是否为此连接启用 TCP 端口共享。</span><span class="sxs-lookup"><span data-stu-id="20374-120">A boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span>  
  
### <a name="teredoenabled"></a><span data-ttu-id="20374-121">TeredoEnabled</span><span class="sxs-lookup"><span data-stu-id="20374-121">TeredoEnabled</span></span>  
 <span data-ttu-id="20374-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="20374-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="20374-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="20374-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20374-124">一个布尔值，指定是否启用 Teredo（一种用于对防火墙后的客户端进行寻址的技术）。</span><span class="sxs-lookup"><span data-stu-id="20374-124">A boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20374-125">要求</span><span class="sxs-lookup"><span data-stu-id="20374-125">Requirements</span></span>  
  
|<span data-ttu-id="20374-126">MOF</span><span class="sxs-lookup"><span data-stu-id="20374-126">MOF</span></span>|<span data-ttu-id="20374-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="20374-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="20374-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="20374-128">Namespace</span></span>|<span data-ttu-id="20374-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="20374-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20374-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="20374-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
