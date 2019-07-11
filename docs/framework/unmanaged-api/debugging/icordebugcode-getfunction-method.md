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
ms.openlocfilehash: 10ab92c660353bea85bbd0918a25f716898ef837
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747532"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="c13da-102">ICorDebugCode::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="c13da-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="c13da-103">获取与此"ICorDebugCode"关联"ICorDebugFunction"。</span><span class="sxs-lookup"><span data-stu-id="c13da-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c13da-104">语法</span><span class="sxs-lookup"><span data-stu-id="c13da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c13da-105">参数</span><span class="sxs-lookup"><span data-stu-id="c13da-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="c13da-106">[out]指向函数的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c13da-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c13da-107">备注</span><span class="sxs-lookup"><span data-stu-id="c13da-107">Remarks</span></span>  
 <span data-ttu-id="c13da-108">`ICorDebugCode` 和`ICorDebugFunction`维护一对一关系。</span><span class="sxs-lookup"><span data-stu-id="c13da-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c13da-109">要求</span><span class="sxs-lookup"><span data-stu-id="c13da-109">Requirements</span></span>  
 <span data-ttu-id="c13da-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c13da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c13da-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c13da-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c13da-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c13da-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c13da-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c13da-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13da-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c13da-114">See also</span></span>
