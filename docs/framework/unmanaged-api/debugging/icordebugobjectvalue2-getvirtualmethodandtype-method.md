---
title: ICorDebugObjectValue2::GetVirtualMethodAndType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
ms.openlocfilehash: 17cb3440c5b33d461b1624608ce115e1942d6beb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129718"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="9361c-102">ICorDebugObjectValue2::GetVirtualMethodAndType 方法</span><span class="sxs-lookup"><span data-stu-id="9361c-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="9361c-103">此方法尚未实现。</span><span class="sxs-lookup"><span data-stu-id="9361c-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9361c-104">语法</span><span class="sxs-lookup"><span data-stu-id="9361c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="9361c-105">备注</span><span class="sxs-lookup"><span data-stu-id="9361c-105">Remarks</span></span>  
 <span data-ttu-id="9361c-106">获取指向 "ICorDebugFunction" 和 "ICorDebugType" 实例的接口指针，这些实例表示指定成员引用的派生程度最高的方法和类型。</span><span class="sxs-lookup"><span data-stu-id="9361c-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9361c-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="9361c-107">See also</span></span>
