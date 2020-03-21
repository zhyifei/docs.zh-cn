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
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179061"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="aa410-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法</span><span class="sxs-lookup"><span data-stu-id="aa410-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="aa410-103">根据应用程序域中的接口标识符获取应用程序域中缓存的 Windows 运行时类型的枚举器。</span><span class="sxs-lookup"><span data-stu-id="aa410-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa410-104">语法</span><span class="sxs-lookup"><span data-stu-id="aa410-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa410-105">parameters</span><span class="sxs-lookup"><span data-stu-id="aa410-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="aa410-106">[在]所需类型的数量。</span><span class="sxs-lookup"><span data-stu-id="aa410-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="aa410-107">[在]指向数组的指针，其中包含与要检索的 Windows 运行时类型的托管表示形式对应的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="aa410-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="aa410-108">[出]指向"ICorDebugTypeEnum"接口对象的地址的指针，该对象允许根据 中的`iidsToResolve`接口标识符检索到已检索的 Windows 运行时类型的缓存托管表示形式。</span><span class="sxs-lookup"><span data-stu-id="aa410-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa410-109">备注</span><span class="sxs-lookup"><span data-stu-id="aa410-109">Remarks</span></span>  
 <span data-ttu-id="aa410-110">如果方法无法检索特定接口标识符的信息，则"ICorDebugTypeEnum"集合中的相应条目将具有一种`ELEMENT_TYPE_END`因数据检索问题或`ELEMENT_TYPE_VOID`未知接口标识符而导致的错误类型。</span><span class="sxs-lookup"><span data-stu-id="aa410-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa410-111">要求</span><span class="sxs-lookup"><span data-stu-id="aa410-111">Requirements</span></span>  
 <span data-ttu-id="aa410-112">**平台：** 窗口运行时</span><span class="sxs-lookup"><span data-stu-id="aa410-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="aa410-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa410-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa410-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa410-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa410-115">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa410-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa410-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa410-116">See also</span></span>

- [<span data-ttu-id="aa410-117">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="aa410-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
