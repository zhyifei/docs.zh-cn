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
ms.openlocfilehash: 88c2513229b6a4183cadbdc78e505910e01e152c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796469"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="c4cbc-102">IEnumDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="c4cbc-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="c4cbc-103">用作`IDefinitionIdentity`对象集合的枚举器。</span><span class="sxs-lookup"><span data-stu-id="c4cbc-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4cbc-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4cbc-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="c4cbc-105">方法</span><span class="sxs-lookup"><span data-stu-id="c4cbc-105">Methods</span></span>  
  
|<span data-ttu-id="c4cbc-106">方法</span><span class="sxs-lookup"><span data-stu-id="c4cbc-106">Method</span></span>|<span data-ttu-id="c4cbc-107">描述</span><span class="sxs-lookup"><span data-stu-id="c4cbc-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="c4cbc-108">获取指向新`IEnumDefinitionIdentity`对象的接口指针，该对象包含与此`IEnumDefinitionIdentity`相同的成员。</span><span class="sxs-lookup"><span data-stu-id="c4cbc-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="c4cbc-109">从当前位置开始，获取`IDefinitionIdentity`指定数目的对象。</span><span class="sxs-lookup"><span data-stu-id="c4cbc-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="c4cbc-110">将指令指针移到此`IEnumDefinitionIdentity`的开头。</span><span class="sxs-lookup"><span data-stu-id="c4cbc-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="c4cbc-111">从当前位置开始，将指令指针向前移动指定数量的元素。</span><span class="sxs-lookup"><span data-stu-id="c4cbc-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4cbc-112">要求</span><span class="sxs-lookup"><span data-stu-id="c4cbc-112">Requirements</span></span>  
 <span data-ttu-id="c4cbc-113">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4cbc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4cbc-114">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="c4cbc-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c4cbc-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4cbc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4cbc-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4cbc-116">See also</span></span>

- [<span data-ttu-id="c4cbc-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="c4cbc-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="c4cbc-118">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="c4cbc-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
