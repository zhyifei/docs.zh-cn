---
title: ICorDebugArrayValue::GetElementAtPosition 方法
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76100116f2ca3a9b9a99477ca2352d5fa1335ab2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502249"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="e7cd6-102">ICorDebugArrayValue::GetElementAtPosition 方法</span><span class="sxs-lookup"><span data-stu-id="e7cd6-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="e7cd6-103">获取位于给定位置，将数组视为从零开始的一维数组的元素。</span><span class="sxs-lookup"><span data-stu-id="e7cd6-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7cd6-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7cd6-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7cd6-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7cd6-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="e7cd6-106">[in]要检索的元素的位置。</span><span class="sxs-lookup"><span data-stu-id="e7cd6-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e7cd6-107">[out]指向一个 ICorDebugValue 对象，表示元素的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="e7cd6-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7cd6-108">备注</span><span class="sxs-lookup"><span data-stu-id="e7cd6-108">Remarks</span></span>  
 <span data-ttu-id="e7cd6-109">多维数组的布局遵循 c + + 样式的数组布局。</span><span class="sxs-lookup"><span data-stu-id="e7cd6-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7cd6-110">要求</span><span class="sxs-lookup"><span data-stu-id="e7cd6-110">Requirements</span></span>  
 <span data-ttu-id="e7cd6-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7cd6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7cd6-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7cd6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7cd6-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7cd6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7cd6-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7cd6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
