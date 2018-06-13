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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9a6978f35b5ea9fb71f8e933dbc7a08b1c390ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416496"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="643ef-102">ICorDebugObjectValue2::GetVirtualMethodAndType 方法</span><span class="sxs-lookup"><span data-stu-id="643ef-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="643ef-103">此方法尚未实现。</span><span class="sxs-lookup"><span data-stu-id="643ef-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="643ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="643ef-104">Syntax</span></span>  
  
```  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="643ef-105">备注</span><span class="sxs-lookup"><span data-stu-id="643ef-105">Remarks</span></span>  
 <span data-ttu-id="643ef-106">获取的接口与"ICorDebugFunction"和"ICorDebugType"的实例表示的派生程度最高的方法和类型的指定的成员引用的指针。</span><span class="sxs-lookup"><span data-stu-id="643ef-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="643ef-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="643ef-107">See Also</span></span>  
    
 
