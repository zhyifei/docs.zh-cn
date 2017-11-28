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
ms.openlocfilehash: 49e1425e8e7e3d09dc36915916b887d2887dccff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="091b4-102">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="091b4-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="091b4-103">用作的集合的枚举数`IReferenceIdentity`对象。</span><span class="sxs-lookup"><span data-stu-id="091b4-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="091b4-104">方法</span><span class="sxs-lookup"><span data-stu-id="091b4-104">Methods</span></span>  
  
|<span data-ttu-id="091b4-105">方法</span><span class="sxs-lookup"><span data-stu-id="091b4-105">Method</span></span>|<span data-ttu-id="091b4-106">描述</span><span class="sxs-lookup"><span data-stu-id="091b4-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="091b4-107">到新获取的接口指针`IEnumReferenceIdentity`，其中包含与此相同的成员`IEnumReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="091b4-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="091b4-108">获取指定的数目的`IReferenceIdentity`对象，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="091b4-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="091b4-109">将指令指针移到此开头`IEnumReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="091b4-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="091b4-110">将指令指针向前移动指定数量的元素，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="091b4-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="091b4-111">要求</span><span class="sxs-lookup"><span data-stu-id="091b4-111">Requirements</span></span>  
 <span data-ttu-id="091b4-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="091b4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="091b4-113">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="091b4-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="091b4-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="091b4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091b4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="091b4-115">See Also</span></span>  
 [<span data-ttu-id="091b4-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="091b4-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="091b4-117">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="091b4-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
