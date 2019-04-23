---
title: Channel 类
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: f60a3946617b0994db1ba9e9ddf43be863be81f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767443"
---
# <a name="channel-class"></a><span data-ttu-id="97ae4-102">Channel 类</span><span class="sxs-lookup"><span data-stu-id="97ae4-102">Channel class</span></span>
<span data-ttu-id="97ae4-103">通道</span><span class="sxs-lookup"><span data-stu-id="97ae4-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ae4-104">语法</span><span class="sxs-lookup"><span data-stu-id="97ae4-104">Syntax</span></span>  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="97ae4-105">方法</span><span class="sxs-lookup"><span data-stu-id="97ae4-105">Methods</span></span>  
 <span data-ttu-id="97ae4-106">Channel 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="97ae4-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="97ae4-107">属性</span><span class="sxs-lookup"><span data-stu-id="97ae4-107">Properties</span></span>  
 <span data-ttu-id="97ae4-108">Channel 类具有以下属性。</span><span class="sxs-lookup"><span data-stu-id="97ae4-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="97ae4-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="97ae4-109">LocalAddress</span></span>  
 <span data-ttu-id="97ae4-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="97ae4-110">Data type: string</span></span>  
  
 <span data-ttu-id="97ae4-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="97ae4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97ae4-112">通道的本地终结点。</span><span class="sxs-lookup"><span data-stu-id="97ae4-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="97ae4-113">ref</span><span class="sxs-lookup"><span data-stu-id="97ae4-113">ref</span></span>  
 <span data-ttu-id="97ae4-114">数据类型：终结点</span><span class="sxs-lookup"><span data-stu-id="97ae4-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="97ae4-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="97ae4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97ae4-116">对通道所连接到的终结点的引用。</span><span class="sxs-lookup"><span data-stu-id="97ae4-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="97ae4-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="97ae4-117">RemoteAddress</span></span>  
 <span data-ttu-id="97ae4-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="97ae4-118">Data type: string</span></span>  
  
 <span data-ttu-id="97ae4-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="97ae4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97ae4-120">与通道相关联的远程地址。</span><span class="sxs-lookup"><span data-stu-id="97ae4-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="97ae4-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="97ae4-121">SessionId</span></span>  
 <span data-ttu-id="97ae4-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="97ae4-122">Data type: string</span></span>  
  
 <span data-ttu-id="97ae4-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="97ae4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97ae4-124">当前会话的 ID（如果有）。</span><span class="sxs-lookup"><span data-stu-id="97ae4-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="97ae4-125">类型</span><span class="sxs-lookup"><span data-stu-id="97ae4-125">Type</span></span>  
 <span data-ttu-id="97ae4-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="97ae4-126">Data type: string</span></span>  
  
 <span data-ttu-id="97ae4-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="97ae4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97ae4-128">通道的类型。</span><span class="sxs-lookup"><span data-stu-id="97ae4-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97ae4-129">要求</span><span class="sxs-lookup"><span data-stu-id="97ae4-129">Requirements</span></span>  
  
|<span data-ttu-id="97ae4-130">MOF</span><span class="sxs-lookup"><span data-stu-id="97ae4-130">MOF</span></span>|<span data-ttu-id="97ae4-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="97ae4-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="97ae4-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="97ae4-132">Namespace</span></span>|<span data-ttu-id="97ae4-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="97ae4-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97ae4-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="97ae4-134">See also</span></span>

- <xref:System.ServiceModel.Channels.ChannelBase>
