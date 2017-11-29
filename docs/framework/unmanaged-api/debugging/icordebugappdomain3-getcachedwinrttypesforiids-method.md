---
title: "ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84b58e3a016431eba10710ea384338cb388404ff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="f29af-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法</span><span class="sxs-lookup"><span data-stu-id="f29af-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="f29af-103">获取一个枚举器，为缓存[!INCLUDE[wrt](../../../../includes/wrt-md.md)]应用程序域中的类型基于其接口标识符。</span><span class="sxs-lookup"><span data-stu-id="f29af-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f29af-104">语法</span><span class="sxs-lookup"><span data-stu-id="f29af-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f29af-105">参数</span><span class="sxs-lookup"><span data-stu-id="f29af-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="f29af-106">[in]所需的类型的数目。</span><span class="sxs-lookup"><span data-stu-id="f29af-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="f29af-107">[in]指向包含对应的托管表示形式的接口标识符的数组的指针[!INCLUDE[wrt](../../../../includes/wrt-md.md)]要检索的类型。</span><span class="sxs-lookup"><span data-stu-id="f29af-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="f29af-108">[out]一个指针指向的地址"ICorDebugTypeEnum"接口对象，它允许枚举的已缓存托管表示形式[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型检索，基于中的接口标识符`iidsToResolve`。</span><span class="sxs-lookup"><span data-stu-id="f29af-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f29af-109">备注</span><span class="sxs-lookup"><span data-stu-id="f29af-109">Remarks</span></span>  
 <span data-ttu-id="f29af-110">如果该方法无法检索有关特定的接口标识符，"ICorDebugTypeEnum"集合中的相应条目将具有一种`ELEMENT_TYPE_END`数据检索问题，由于错误或`ELEMENT_TYPE_VOID`未知接口标识符。</span><span class="sxs-lookup"><span data-stu-id="f29af-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f29af-111">要求</span><span class="sxs-lookup"><span data-stu-id="f29af-111">Requirements</span></span>  
 <span data-ttu-id="f29af-112">**平台：**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f29af-112">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="f29af-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f29af-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f29af-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f29af-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f29af-115">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f29af-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29af-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f29af-116">See Also</span></span>  
 [<span data-ttu-id="f29af-117">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="f29af-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
