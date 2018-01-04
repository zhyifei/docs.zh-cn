---
title: "IEnumReferenceIdentity 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumReferenceIdentity
helpviewer_keywords: IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1af31c72770947c33f358a9689bac6fd95ef53c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="602df-102">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="602df-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="602df-103">用作的集合的枚举数`IReferenceIdentity`对象。</span><span class="sxs-lookup"><span data-stu-id="602df-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="602df-104">方法</span><span class="sxs-lookup"><span data-stu-id="602df-104">Methods</span></span>  
  
|<span data-ttu-id="602df-105">方法</span><span class="sxs-lookup"><span data-stu-id="602df-105">Method</span></span>|<span data-ttu-id="602df-106">描述</span><span class="sxs-lookup"><span data-stu-id="602df-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="602df-107">到新获取的接口指针`IEnumReferenceIdentity`，其中包含与此相同的成员`IEnumReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="602df-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="602df-108">获取指定的数目的`IReferenceIdentity`对象，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="602df-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="602df-109">将指令指针移到此开头`IEnumReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="602df-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="602df-110">将指令指针向前移动指定数量的元素，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="602df-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="602df-111">惠?</span><span class="sxs-lookup"><span data-stu-id="602df-111">Requirements</span></span>  
 <span data-ttu-id="602df-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="602df-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="602df-113">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="602df-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="602df-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="602df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602df-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="602df-115">See Also</span></span>  
 [<span data-ttu-id="602df-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="602df-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="602df-117">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="602df-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
