---
title: IEnumDefinitionIdentity 接口
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3ff37acd9b4dffe80112f0a0ebe9c9cd86ae66f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668440"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="45f83-102">IEnumDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="45f83-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="45f83-103">用作集合的枚举器`IDefinitionIdentity`对象。</span><span class="sxs-lookup"><span data-stu-id="45f83-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45f83-104">语法</span><span class="sxs-lookup"><span data-stu-id="45f83-104">Syntax</span></span>  
  
```  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="45f83-105">方法</span><span class="sxs-lookup"><span data-stu-id="45f83-105">Methods</span></span>  
  
|<span data-ttu-id="45f83-106">方法</span><span class="sxs-lookup"><span data-stu-id="45f83-106">Method</span></span>|<span data-ttu-id="45f83-107">描述</span><span class="sxs-lookup"><span data-stu-id="45f83-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="45f83-108">为新获取的接口指针`IEnumDefinitionIdentity`对象，其中包含与此相同的成员`IEnumDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="45f83-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="45f83-109">获取指定的数目的`IDefinitionIdentity`对象，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="45f83-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="45f83-110">将指令指针移到开头`IEnumDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="45f83-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="45f83-111">按指定数量的元素，从当前位置开始移动指令指针前进。</span><span class="sxs-lookup"><span data-stu-id="45f83-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45f83-112">要求</span><span class="sxs-lookup"><span data-stu-id="45f83-112">Requirements</span></span>  
 <span data-ttu-id="45f83-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45f83-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45f83-114">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="45f83-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="45f83-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45f83-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f83-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="45f83-116">See also</span></span>
- [<span data-ttu-id="45f83-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="45f83-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="45f83-118">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="45f83-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
