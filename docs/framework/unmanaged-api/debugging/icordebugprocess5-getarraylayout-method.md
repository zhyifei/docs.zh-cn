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
ms.openlocfilehash: 332de11790e78b712a429365bd89cc9e41539edc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105516"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="5bda9-102">ICorDebugProcess5::GetArrayLayout 方法</span><span class="sxs-lookup"><span data-stu-id="5bda9-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="5bda9-103">提供的布局信息的数组类型。</span><span class="sxs-lookup"><span data-stu-id="5bda9-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bda9-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bda9-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bda9-105">参数</span><span class="sxs-lookup"><span data-stu-id="5bda9-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="5bda9-106">[in]一个[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标记，用于指定需要其布局的数组。</span><span class="sxs-lookup"><span data-stu-id="5bda9-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="5bda9-107">[out]一个指向[COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)结构，其中包含在内存中数组的布局信息。</span><span class="sxs-lookup"><span data-stu-id="5bda9-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bda9-108">备注</span><span class="sxs-lookup"><span data-stu-id="5bda9-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bda9-109">要求</span><span class="sxs-lookup"><span data-stu-id="5bda9-109">Requirements</span></span>  
 <span data-ttu-id="5bda9-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bda9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bda9-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bda9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bda9-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bda9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bda9-113">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bda9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bda9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bda9-114">See also</span></span>

- [<span data-ttu-id="5bda9-115">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="5bda9-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="5bda9-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="5bda9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
