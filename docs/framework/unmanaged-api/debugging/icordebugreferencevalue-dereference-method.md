---
title: ICorDebugReferenceValue::Dereference 方法
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b436fa14322d444a6c8b515ba8e50698eecb95ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487013"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="585fa-102">ICorDebugReferenceValue::Dereference 方法</span><span class="sxs-lookup"><span data-stu-id="585fa-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="585fa-103">获取引用的对象。</span><span class="sxs-lookup"><span data-stu-id="585fa-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="585fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="585fa-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="585fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="585fa-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="585fa-106">[out]指向表示此 ICorDebugReferenceValue 对象所指向的对象 ICorDebugValue 的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="585fa-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="585fa-107">备注</span><span class="sxs-lookup"><span data-stu-id="585fa-107">Remarks</span></span>  
 <span data-ttu-id="585fa-108">`ICorDebugValue`仅在它的引用尚未被禁用时，对象是否有效。</span><span class="sxs-lookup"><span data-stu-id="585fa-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="585fa-109">要求</span><span class="sxs-lookup"><span data-stu-id="585fa-109">Requirements</span></span>  
 <span data-ttu-id="585fa-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="585fa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="585fa-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="585fa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="585fa-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="585fa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="585fa-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="585fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
