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
ms.openlocfilehash: 09c6431ec885c8b797dc9bb5f5c3ffe21890ccc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107943"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="0ed72-102">IEnumDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="0ed72-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="0ed72-103">用作 `IDefinitionIdentity` 对象的集合的枚举器。</span><span class="sxs-lookup"><span data-stu-id="0ed72-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ed72-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ed72-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="0ed72-105">方法</span><span class="sxs-lookup"><span data-stu-id="0ed72-105">Methods</span></span>  
  
|<span data-ttu-id="0ed72-106">方法</span><span class="sxs-lookup"><span data-stu-id="0ed72-106">Method</span></span>|<span data-ttu-id="0ed72-107">描述</span><span class="sxs-lookup"><span data-stu-id="0ed72-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="0ed72-108">获取一个指向新 `IEnumDefinitionIdentity` 对象的接口指针，该对象包含与此 `IEnumDefinitionIdentity`相同的成员。</span><span class="sxs-lookup"><span data-stu-id="0ed72-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="0ed72-109">从当前位置开始，获取指定数目的 `IDefinitionIdentity` 对象。</span><span class="sxs-lookup"><span data-stu-id="0ed72-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="0ed72-110">将指令指针移动到此 `IEnumDefinitionIdentity`的开头。</span><span class="sxs-lookup"><span data-stu-id="0ed72-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="0ed72-111">从当前位置开始，将指令指针向前移动指定数量的元素。</span><span class="sxs-lookup"><span data-stu-id="0ed72-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ed72-112">要求</span><span class="sxs-lookup"><span data-stu-id="0ed72-112">Requirements</span></span>  
 <span data-ttu-id="0ed72-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed72-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ed72-114">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="0ed72-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="0ed72-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ed72-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed72-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ed72-116">See also</span></span>

- [<span data-ttu-id="0ed72-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="0ed72-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="0ed72-118">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="0ed72-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
