---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ef8d1c47275d3cbd69c1516b788b950f8535513
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737719"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="dc6c3-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法</span><span class="sxs-lookup"><span data-stu-id="dc6c3-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="dc6c3-103">获取在基于其接口标识符的应用程序域中已缓存的 Windows 运行时类型的枚举器。</span><span class="sxs-lookup"><span data-stu-id="dc6c3-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc6c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="dc6c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc6c3-105">参数</span><span class="sxs-lookup"><span data-stu-id="dc6c3-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="dc6c3-106">[in]所需类型的数目。</span><span class="sxs-lookup"><span data-stu-id="dc6c3-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="dc6c3-107">[in]指向包含对应于要检索的 Windows 运行时类型的托管表示形式的接口标识符的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="dc6c3-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="dc6c3-108">[out]检索到允许的缓存托管表示形式的 Windows 运行时类型的枚举的"ICorDebugTypeEnum"接口对象地址的指针，根据中的接口标识符`iidsToResolve`。</span><span class="sxs-lookup"><span data-stu-id="dc6c3-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc6c3-109">备注</span><span class="sxs-lookup"><span data-stu-id="dc6c3-109">Remarks</span></span>  
 <span data-ttu-id="dc6c3-110">如果该方法无法检索特定的接口标识符的信息，"ICorDebugTypeEnum"集合中的相应项将具有类型`ELEMENT_TYPE_END`的数据检索问题导致的错误或`ELEMENT_TYPE_VOID`未知接口标识符。</span><span class="sxs-lookup"><span data-stu-id="dc6c3-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6c3-111">要求</span><span class="sxs-lookup"><span data-stu-id="dc6c3-111">Requirements</span></span>  
 <span data-ttu-id="dc6c3-112">**平台：** Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="dc6c3-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="dc6c3-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc6c3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc6c3-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc6c3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc6c3-115">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6c3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6c3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc6c3-116">See also</span></span>

- [<span data-ttu-id="dc6c3-117">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="dc6c3-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
