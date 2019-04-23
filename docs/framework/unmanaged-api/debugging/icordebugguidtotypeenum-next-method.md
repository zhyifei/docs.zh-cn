---
title: ICorDebugGuidToTypeEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f48c142b2b3742d01a8f796f11d5c9174529a041
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105814"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="12017-102">ICorDebugGuidToTypeEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="12017-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="12017-103">获取指定的数目的[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)映射 Guid 类型信息的实例。</span><span class="sxs-lookup"><span data-stu-id="12017-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12017-104">语法</span><span class="sxs-lookup"><span data-stu-id="12017-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12017-105">参数</span><span class="sxs-lookup"><span data-stu-id="12017-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="12017-106">[in]要检索的 GUID 类型映射对象的数目。</span><span class="sxs-lookup"><span data-stu-id="12017-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="12017-107">[out]一个指针，其中每个指向数组[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)映射对象[!INCLUDE[wrt](../../../../includes/wrt-md.md)]GUID 传递给其相应的 ICorDebugType 对象。</span><span class="sxs-lookup"><span data-stu-id="12017-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="12017-108">[out]指向数[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)对象中实际返回`values`。</span><span class="sxs-lookup"><span data-stu-id="12017-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12017-109">备注</span><span class="sxs-lookup"><span data-stu-id="12017-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12017-110">要求</span><span class="sxs-lookup"><span data-stu-id="12017-110">Requirements</span></span>  
 <span data-ttu-id="12017-111">**平台：** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12017-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="12017-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12017-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12017-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12017-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12017-114">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12017-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12017-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="12017-115">See also</span></span>

- [<span data-ttu-id="12017-116">ICorDebugGuidToTypeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="12017-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="12017-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="12017-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
