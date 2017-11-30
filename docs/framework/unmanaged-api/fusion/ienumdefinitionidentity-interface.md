---
title: "IEnumDefinitionIdentity 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumDefinitionIdentity
helpviewer_keywords: IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc1f3a46ac7da58fb2c209f833173a1bc6b32ea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="83c50-102">IEnumDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="83c50-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="83c50-103">用作的集合的枚举数`IDefinitionIdentity`对象。</span><span class="sxs-lookup"><span data-stu-id="83c50-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c50-104">语法</span><span class="sxs-lookup"><span data-stu-id="83c50-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="83c50-105">方法</span><span class="sxs-lookup"><span data-stu-id="83c50-105">Methods</span></span>  
  
|<span data-ttu-id="83c50-106">方法</span><span class="sxs-lookup"><span data-stu-id="83c50-106">Method</span></span>|<span data-ttu-id="83c50-107">描述</span><span class="sxs-lookup"><span data-stu-id="83c50-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="83c50-108">到新获取的接口指针`IEnumDefinitionIdentity`对象，其中包含与此相同的成员`IEnumDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="83c50-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="83c50-109">获取指定的数目的`IDefinitionIdentity`对象，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="83c50-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="83c50-110">将指令指针移到此开头`IEnumDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="83c50-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="83c50-111">将指令指针向前移动指定数量的元素，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="83c50-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83c50-112">要求</span><span class="sxs-lookup"><span data-stu-id="83c50-112">Requirements</span></span>  
 <span data-ttu-id="83c50-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83c50-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c50-114">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="83c50-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="83c50-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83c50-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c50-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83c50-116">See Also</span></span>  
 [<span data-ttu-id="83c50-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="83c50-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="83c50-118">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="83c50-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
