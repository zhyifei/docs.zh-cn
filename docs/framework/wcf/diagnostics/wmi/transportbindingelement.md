---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 303e5523befb68c65bc50ee3933af58897929363
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668442"
---
# <a name="transportbindingelement"></a><span data-ttu-id="778a7-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="778a7-102">TransportBindingElement</span></span>
<span data-ttu-id="778a7-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="778a7-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="778a7-104">语法</span><span class="sxs-lookup"><span data-stu-id="778a7-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="778a7-105">方法</span><span class="sxs-lookup"><span data-stu-id="778a7-105">Methods</span></span>  
 <span data-ttu-id="778a7-106">TransportBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="778a7-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="778a7-107">Properties</span><span class="sxs-lookup"><span data-stu-id="778a7-107">Properties</span></span>  
 <span data-ttu-id="778a7-108">TransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="778a7-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="778a7-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="778a7-109">ManualAddressing</span></span>  
 <span data-ttu-id="778a7-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="778a7-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="778a7-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="778a7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="778a7-112">一个布尔值，该值指定用户是否要控制消息寻址。</span><span class="sxs-lookup"><span data-stu-id="778a7-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="778a7-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="778a7-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="778a7-114">数据类型：sint64</span><span class="sxs-lookup"><span data-stu-id="778a7-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="778a7-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="778a7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="778a7-116">绑定的最大缓冲池大小。</span><span class="sxs-lookup"><span data-stu-id="778a7-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="778a7-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="778a7-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="778a7-118">数据类型：sint64</span><span class="sxs-lookup"><span data-stu-id="778a7-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="778a7-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="778a7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="778a7-120">此绑定所处理的消息的最大大小。</span><span class="sxs-lookup"><span data-stu-id="778a7-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="778a7-121">方案</span><span class="sxs-lookup"><span data-stu-id="778a7-121">Scheme</span></span>  
 <span data-ttu-id="778a7-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="778a7-122">Data type: string</span></span>  
  
 <span data-ttu-id="778a7-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="778a7-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="778a7-124">传输的 URI 方案。</span><span class="sxs-lookup"><span data-stu-id="778a7-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="778a7-125">要求</span><span class="sxs-lookup"><span data-stu-id="778a7-125">Requirements</span></span>  
  
|<span data-ttu-id="778a7-126">MOF</span><span class="sxs-lookup"><span data-stu-id="778a7-126">MOF</span></span>|<span data-ttu-id="778a7-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="778a7-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="778a7-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="778a7-128">Namespace</span></span>|<span data-ttu-id="778a7-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="778a7-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="778a7-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="778a7-130">See also</span></span>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
