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
ms.openlocfilehash: 601110d37fabbff01aeb14d8ca69a27a2463353f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491398"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="e7648-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法</span><span class="sxs-lookup"><span data-stu-id="e7648-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="e7648-103">获取一个枚举器的缓存[!INCLUDE[wrt](../../../../includes/wrt-md.md)]应用程序域中的类型基于其接口标识符。</span><span class="sxs-lookup"><span data-stu-id="e7648-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7648-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7648-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7648-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7648-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="e7648-106">[in]所需类型的数目。</span><span class="sxs-lookup"><span data-stu-id="e7648-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="e7648-107">[in]指向包含对应的托管表示形式的接口标识符的数组的指针[!INCLUDE[wrt](../../../../includes/wrt-md.md)]要检索的类型。</span><span class="sxs-lookup"><span data-stu-id="e7648-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="e7648-108">[out]指向将允许枚举的已缓存的"ICorDebugTypeEnum"接口对象地址的管理的表示形式[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型检索，根据中的接口标识符`iidsToResolve`。</span><span class="sxs-lookup"><span data-stu-id="e7648-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7648-109">备注</span><span class="sxs-lookup"><span data-stu-id="e7648-109">Remarks</span></span>  
 <span data-ttu-id="e7648-110">如果该方法无法检索特定的接口标识符的信息，"ICorDebugTypeEnum"集合中的相应项将具有类型`ELEMENT_TYPE_END`的数据检索问题导致的错误或`ELEMENT_TYPE_VOID`未知接口标识符。</span><span class="sxs-lookup"><span data-stu-id="e7648-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7648-111">要求</span><span class="sxs-lookup"><span data-stu-id="e7648-111">Requirements</span></span>  
 <span data-ttu-id="e7648-112">**平台：** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7648-112">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="e7648-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7648-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7648-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7648-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7648-115">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7648-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7648-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7648-116">See also</span></span>
- [<span data-ttu-id="e7648-117">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="e7648-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
