---
title: ICorDebugProcess5::GetArrayLayout 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5cff3f3f577a0c7ef04a226ec70a2722c89b5c8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496880"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="29710-102">ICorDebugProcess5::GetArrayLayout 方法</span><span class="sxs-lookup"><span data-stu-id="29710-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="29710-103">提供的布局信息的数组类型。</span><span class="sxs-lookup"><span data-stu-id="29710-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29710-104">语法</span><span class="sxs-lookup"><span data-stu-id="29710-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29710-105">参数</span><span class="sxs-lookup"><span data-stu-id="29710-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="29710-106">[in]一个[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标记，用于指定需要其布局的数组。</span><span class="sxs-lookup"><span data-stu-id="29710-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="29710-107">[out]一个指向[COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)结构，其中包含在内存中数组的布局信息。</span><span class="sxs-lookup"><span data-stu-id="29710-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29710-108">备注</span><span class="sxs-lookup"><span data-stu-id="29710-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29710-109">要求</span><span class="sxs-lookup"><span data-stu-id="29710-109">Requirements</span></span>  
 <span data-ttu-id="29710-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="29710-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29710-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29710-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29710-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29710-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29710-113">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29710-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29710-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="29710-114">See also</span></span>
- [<span data-ttu-id="29710-115">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="29710-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="29710-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="29710-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
