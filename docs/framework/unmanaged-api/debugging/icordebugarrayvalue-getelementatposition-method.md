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
ms.openlocfilehash: 10584442d7e0bd61e6decaf2b494dfe39f339d6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088418"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="ad646-102">ICorDebugArrayValue::GetElementAtPosition 方法</span><span class="sxs-lookup"><span data-stu-id="ad646-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="ad646-103">获取位于给定位置的元素，并将该数组视为从零开始的一维数组。</span><span class="sxs-lookup"><span data-stu-id="ad646-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad646-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad646-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad646-105">参数</span><span class="sxs-lookup"><span data-stu-id="ad646-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="ad646-106">中要检索的元素的位置。</span><span class="sxs-lookup"><span data-stu-id="ad646-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ad646-107">弄指向表示元素值的 ICorDebugValue 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="ad646-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad646-108">备注</span><span class="sxs-lookup"><span data-stu-id="ad646-108">Remarks</span></span>  
 <span data-ttu-id="ad646-109">多维数组的布局遵循数组布局的C++样式。</span><span class="sxs-lookup"><span data-stu-id="ad646-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad646-110">要求</span><span class="sxs-lookup"><span data-stu-id="ad646-110">Requirements</span></span>  
 <span data-ttu-id="ad646-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad646-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad646-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad646-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad646-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad646-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad646-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad646-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
