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
ms.openlocfilehash: 8b259636a8bd28abd3bba12c4a05dda3c13557e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784895"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="eb163-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 方法</span><span class="sxs-lookup"><span data-stu-id="eb163-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="eb163-103">基于其接口标识符获取应用程序域中缓存的 Windows 运行时类型的枚举器。</span><span class="sxs-lookup"><span data-stu-id="eb163-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb163-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb163-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb163-105">参数</span><span class="sxs-lookup"><span data-stu-id="eb163-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="eb163-106">中所需类型的数目。</span><span class="sxs-lookup"><span data-stu-id="eb163-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="eb163-107">中指向数组的指针，该数组包含与要检索的 Windows 运行时类型的托管表示形式对应的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="eb163-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="eb163-108">弄一个指向 "ICorDebugTypeEnum" 接口对象地址的指针，该对象允许基于 `iidsToResolve`中的接口标识符枚举检索到的 Windows 运行时类型的缓存托管表示形式。</span><span class="sxs-lookup"><span data-stu-id="eb163-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb163-109">备注</span><span class="sxs-lookup"><span data-stu-id="eb163-109">Remarks</span></span>  
 <span data-ttu-id="eb163-110">如果该方法无法检索特定接口标识符的信息，则 "ICorDebugTypeEnum" 集合中的对应条目将有一种类型的 `ELEMENT_TYPE_END` 用于错误，这是由于数据检索问题或未知接口标识符 `ELEMENT_TYPE_VOID` 的。</span><span class="sxs-lookup"><span data-stu-id="eb163-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb163-111">需求</span><span class="sxs-lookup"><span data-stu-id="eb163-111">Requirements</span></span>  
 <span data-ttu-id="eb163-112">**平台：** Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="eb163-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="eb163-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb163-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb163-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb163-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb163-115">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb163-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb163-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb163-116">See also</span></span>

- [<span data-ttu-id="eb163-117">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="eb163-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
