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
ms.openlocfilehash: d19ca92db6f57a004dca54f6e22db10603c9498a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697324"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="7f740-102">IEnumDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="7f740-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="7f740-103">用作集合的枚举器`IDefinitionIdentity`对象。</span><span class="sxs-lookup"><span data-stu-id="7f740-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f740-104">语法</span><span class="sxs-lookup"><span data-stu-id="7f740-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="7f740-105">方法</span><span class="sxs-lookup"><span data-stu-id="7f740-105">Methods</span></span>  
  
|<span data-ttu-id="7f740-106">方法</span><span class="sxs-lookup"><span data-stu-id="7f740-106">Method</span></span>|<span data-ttu-id="7f740-107">描述</span><span class="sxs-lookup"><span data-stu-id="7f740-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="7f740-108">为新获取的接口指针`IEnumDefinitionIdentity`对象，其中包含与此相同的成员`IEnumDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="7f740-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="7f740-109">获取指定的数目的`IDefinitionIdentity`对象，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="7f740-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="7f740-110">将指令指针移到开头`IEnumDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="7f740-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="7f740-111">按指定数量的元素，从当前位置开始移动指令指针前进。</span><span class="sxs-lookup"><span data-stu-id="7f740-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f740-112">要求</span><span class="sxs-lookup"><span data-stu-id="7f740-112">Requirements</span></span>  
 <span data-ttu-id="7f740-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f740-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f740-114">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="7f740-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="7f740-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f740-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f740-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f740-116">See also</span></span>

- [<span data-ttu-id="7f740-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="7f740-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="7f740-118">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="7f740-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
