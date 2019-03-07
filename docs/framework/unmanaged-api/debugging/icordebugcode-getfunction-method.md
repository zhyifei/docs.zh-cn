---
title: ICorDebugCode::GetFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5d8168649f6a0c75844da0ee68bf3782efc9024
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483857"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="5e00d-102">ICorDebugCode::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="5e00d-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="5e00d-103">获取与此"ICorDebugCode"关联"ICorDebugFunction"。</span><span class="sxs-lookup"><span data-stu-id="5e00d-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e00d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5e00d-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e00d-105">参数</span><span class="sxs-lookup"><span data-stu-id="5e00d-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="5e00d-106">[out]指向函数的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="5e00d-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e00d-107">备注</span><span class="sxs-lookup"><span data-stu-id="5e00d-107">Remarks</span></span>  
 <span data-ttu-id="5e00d-108">`ICorDebugCode` 和`ICorDebugFunction`维护一对一关系。</span><span class="sxs-lookup"><span data-stu-id="5e00d-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e00d-109">要求</span><span class="sxs-lookup"><span data-stu-id="5e00d-109">Requirements</span></span>  
 <span data-ttu-id="5e00d-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e00d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e00d-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e00d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e00d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e00d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e00d-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e00d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e00d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e00d-114">See also</span></span>

