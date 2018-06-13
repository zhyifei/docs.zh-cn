---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: dc7a29e5911a9d0a774e36f5be8c1f3cacad69b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486612"
---
# <a name="transportbindingelement"></a><span data-ttu-id="09d28-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="09d28-102">TransportBindingElement</span></span>
<span data-ttu-id="09d28-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="09d28-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d28-104">语法</span><span class="sxs-lookup"><span data-stu-id="09d28-104">Syntax</span></span>  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="09d28-105">方法</span><span class="sxs-lookup"><span data-stu-id="09d28-105">Methods</span></span>  
 <span data-ttu-id="09d28-106">TransportBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="09d28-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="09d28-107">属性</span><span class="sxs-lookup"><span data-stu-id="09d28-107">Properties</span></span>  
 <span data-ttu-id="09d28-108">TransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="09d28-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="09d28-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="09d28-109">ManualAddressing</span></span>  
 <span data-ttu-id="09d28-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="09d28-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="09d28-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="09d28-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09d28-112">一个布尔值，该值指定用户是否要控制消息寻址。</span><span class="sxs-lookup"><span data-stu-id="09d28-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="09d28-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="09d28-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="09d28-114">数据类型：sint64</span><span class="sxs-lookup"><span data-stu-id="09d28-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="09d28-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="09d28-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09d28-116">绑定的最大缓冲池大小。</span><span class="sxs-lookup"><span data-stu-id="09d28-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="09d28-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="09d28-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="09d28-118">数据类型：sint64</span><span class="sxs-lookup"><span data-stu-id="09d28-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="09d28-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="09d28-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09d28-120">此绑定所处理的消息的最大大小。</span><span class="sxs-lookup"><span data-stu-id="09d28-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="09d28-121">方案</span><span class="sxs-lookup"><span data-stu-id="09d28-121">Scheme</span></span>  
 <span data-ttu-id="09d28-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="09d28-122">Data type: string</span></span>  
  
 <span data-ttu-id="09d28-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="09d28-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="09d28-124">传输的 URI 方案。</span><span class="sxs-lookup"><span data-stu-id="09d28-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09d28-125">要求</span><span class="sxs-lookup"><span data-stu-id="09d28-125">Requirements</span></span>  
  
|<span data-ttu-id="09d28-126">MOF</span><span class="sxs-lookup"><span data-stu-id="09d28-126">MOF</span></span>|<span data-ttu-id="09d28-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="09d28-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="09d28-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="09d28-128">Namespace</span></span>|<span data-ttu-id="09d28-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="09d28-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09d28-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="09d28-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
