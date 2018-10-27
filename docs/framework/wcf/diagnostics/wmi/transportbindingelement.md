---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 79d8b1f4a5127ca36eb57954cff6ee6a97e55e41
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182653"
---
# <a name="transportbindingelement"></a><span data-ttu-id="0856d-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0856d-102">TransportBindingElement</span></span>
<span data-ttu-id="0856d-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="0856d-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0856d-104">语法</span><span class="sxs-lookup"><span data-stu-id="0856d-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0856d-105">方法</span><span class="sxs-lookup"><span data-stu-id="0856d-105">Methods</span></span>  
 <span data-ttu-id="0856d-106">TransportBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="0856d-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0856d-107">属性</span><span class="sxs-lookup"><span data-stu-id="0856d-107">Properties</span></span>  
 <span data-ttu-id="0856d-108">TransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="0856d-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="0856d-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="0856d-109">ManualAddressing</span></span>  
 <span data-ttu-id="0856d-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0856d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="0856d-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0856d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0856d-112">一个布尔值，该值指定用户是否要控制消息寻址。</span><span class="sxs-lookup"><span data-stu-id="0856d-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="0856d-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="0856d-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="0856d-114">数据类型：sint64</span><span class="sxs-lookup"><span data-stu-id="0856d-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="0856d-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0856d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0856d-116">绑定的最大缓冲池大小。</span><span class="sxs-lookup"><span data-stu-id="0856d-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="0856d-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="0856d-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="0856d-118">数据类型：sint64</span><span class="sxs-lookup"><span data-stu-id="0856d-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="0856d-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0856d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0856d-120">此绑定所处理的消息的最大大小。</span><span class="sxs-lookup"><span data-stu-id="0856d-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="0856d-121">方案</span><span class="sxs-lookup"><span data-stu-id="0856d-121">Scheme</span></span>  
 <span data-ttu-id="0856d-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0856d-122">Data type: string</span></span>  
  
 <span data-ttu-id="0856d-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0856d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0856d-124">传输的 URI 方案。</span><span class="sxs-lookup"><span data-stu-id="0856d-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0856d-125">要求</span><span class="sxs-lookup"><span data-stu-id="0856d-125">Requirements</span></span>  
  
|<span data-ttu-id="0856d-126">MOF</span><span class="sxs-lookup"><span data-stu-id="0856d-126">MOF</span></span>|<span data-ttu-id="0856d-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="0856d-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0856d-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="0856d-128">Namespace</span></span>|<span data-ttu-id="0856d-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="0856d-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0856d-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="0856d-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
