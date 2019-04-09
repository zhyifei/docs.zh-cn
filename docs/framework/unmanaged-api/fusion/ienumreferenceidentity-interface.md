---
title: IEnumReferenceIdentity 接口
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 766b17bae0c58d9872ff9c118f330ebc3220257e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123482"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="85f3a-102">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="85f3a-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="85f3a-103">用作集合的枚举数`IReferenceIdentity`对象。</span><span class="sxs-lookup"><span data-stu-id="85f3a-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85f3a-104">方法</span><span class="sxs-lookup"><span data-stu-id="85f3a-104">Methods</span></span>  
  
|<span data-ttu-id="85f3a-105">方法</span><span class="sxs-lookup"><span data-stu-id="85f3a-105">Method</span></span>|<span data-ttu-id="85f3a-106">描述</span><span class="sxs-lookup"><span data-stu-id="85f3a-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="85f3a-107">为新获取的接口指针`IEnumReferenceIdentity`，其中包含与此相同的成员`IEnumReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="85f3a-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="85f3a-108">获取指定的数目的`IReferenceIdentity`对象，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="85f3a-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="85f3a-109">将指令指针移到开头`IEnumReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="85f3a-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="85f3a-110">按指定数量的元素，从当前位置开始移动指令指针前进。</span><span class="sxs-lookup"><span data-stu-id="85f3a-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85f3a-111">要求</span><span class="sxs-lookup"><span data-stu-id="85f3a-111">Requirements</span></span>  
 <span data-ttu-id="85f3a-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85f3a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85f3a-113">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="85f3a-113">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="85f3a-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="85f3a-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="85f3a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="85f3a-115">See also</span></span>

- [<span data-ttu-id="85f3a-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="85f3a-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="85f3a-117">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="85f3a-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
