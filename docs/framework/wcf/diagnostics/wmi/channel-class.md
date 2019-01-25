---
title: Channel 类
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 3fbf398cca7ae9adbbecb9439bf3cbd32eb03969
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668387"
---
# <a name="channel-class"></a><span data-ttu-id="e15a3-102">Channel 类</span><span class="sxs-lookup"><span data-stu-id="e15a3-102">Channel class</span></span>
<span data-ttu-id="e15a3-103">通道</span><span class="sxs-lookup"><span data-stu-id="e15a3-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e15a3-104">语法</span><span class="sxs-lookup"><span data-stu-id="e15a3-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="e15a3-105">方法</span><span class="sxs-lookup"><span data-stu-id="e15a3-105">Methods</span></span>  
 <span data-ttu-id="e15a3-106">Channel 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="e15a3-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e15a3-107">属性</span><span class="sxs-lookup"><span data-stu-id="e15a3-107">Properties</span></span>  
 <span data-ttu-id="e15a3-108">Channel 类具有以下属性。</span><span class="sxs-lookup"><span data-stu-id="e15a3-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="e15a3-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="e15a3-109">LocalAddress</span></span>  
 <span data-ttu-id="e15a3-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e15a3-110">Data type: string</span></span>  
  
 <span data-ttu-id="e15a3-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e15a3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e15a3-112">通道的本地终结点。</span><span class="sxs-lookup"><span data-stu-id="e15a3-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="e15a3-113">ref</span><span class="sxs-lookup"><span data-stu-id="e15a3-113">ref</span></span>  
 <span data-ttu-id="e15a3-114">数据类型：终结点</span><span class="sxs-lookup"><span data-stu-id="e15a3-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="e15a3-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e15a3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e15a3-116">对通道所连接到的终结点的引用。</span><span class="sxs-lookup"><span data-stu-id="e15a3-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="e15a3-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="e15a3-117">RemoteAddress</span></span>  
 <span data-ttu-id="e15a3-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e15a3-118">Data type: string</span></span>  
  
 <span data-ttu-id="e15a3-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e15a3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e15a3-120">与通道相关联的远程地址。</span><span class="sxs-lookup"><span data-stu-id="e15a3-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="e15a3-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="e15a3-121">SessionId</span></span>  
 <span data-ttu-id="e15a3-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e15a3-122">Data type: string</span></span>  
  
 <span data-ttu-id="e15a3-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e15a3-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e15a3-124">当前会话的 ID（如果有）。</span><span class="sxs-lookup"><span data-stu-id="e15a3-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="e15a3-125">类型</span><span class="sxs-lookup"><span data-stu-id="e15a3-125">Type</span></span>  
 <span data-ttu-id="e15a3-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e15a3-126">Data type: string</span></span>  
  
 <span data-ttu-id="e15a3-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e15a3-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e15a3-128">通道的类型。</span><span class="sxs-lookup"><span data-stu-id="e15a3-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e15a3-129">要求</span><span class="sxs-lookup"><span data-stu-id="e15a3-129">Requirements</span></span>  
  
|<span data-ttu-id="e15a3-130">MOF</span><span class="sxs-lookup"><span data-stu-id="e15a3-130">MOF</span></span>|<span data-ttu-id="e15a3-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="e15a3-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e15a3-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="e15a3-132">Namespace</span></span>|<span data-ttu-id="e15a3-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="e15a3-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e15a3-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="e15a3-134">See also</span></span>
- <xref:System.ServiceModel.Channels.ChannelBase>
