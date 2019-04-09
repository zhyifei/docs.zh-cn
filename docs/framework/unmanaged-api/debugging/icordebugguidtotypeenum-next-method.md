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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105814"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="f61ce-102">ICorDebugGuidToTypeEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="f61ce-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="f61ce-103">获取指定的数目的[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)映射 Guid 类型信息的实例。</span><span class="sxs-lookup"><span data-stu-id="f61ce-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f61ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="f61ce-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f61ce-105">参数</span><span class="sxs-lookup"><span data-stu-id="f61ce-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f61ce-106">[in]要检索的 GUID 类型映射对象的数目。</span><span class="sxs-lookup"><span data-stu-id="f61ce-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="f61ce-107">[out]一个指针，其中每个指向数组[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)映射对象[!INCLUDE[wrt](../../../../includes/wrt-md.md)]GUID 传递给其相应的 ICorDebugType 对象。</span><span class="sxs-lookup"><span data-stu-id="f61ce-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f61ce-108">[out]指向数[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)对象中实际返回`values`。</span><span class="sxs-lookup"><span data-stu-id="f61ce-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f61ce-109">备注</span><span class="sxs-lookup"><span data-stu-id="f61ce-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f61ce-110">要求</span><span class="sxs-lookup"><span data-stu-id="f61ce-110">Requirements</span></span>  
 **<span data-ttu-id="f61ce-111">平台：</span><span class="sxs-lookup"><span data-stu-id="f61ce-111">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="f61ce-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f61ce-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f61ce-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f61ce-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f61ce-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f61ce-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f61ce-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f61ce-115">See also</span></span>

- [<span data-ttu-id="f61ce-116">ICorDebugGuidToTypeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="f61ce-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="f61ce-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="f61ce-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
