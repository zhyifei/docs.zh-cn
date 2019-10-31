---
title: ICorDebugFunctionBreakpoint::GetFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
ms.openlocfilehash: 0b53c80157bfd99a766eb691e8a8a2e6b9659a95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137751"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="baadb-102">ICorDebugFunctionBreakpoint::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="baadb-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="baadb-103">获取一个指向 ICorDebugFunction 的接口指针，该指针引用在其中设置断点的函数。</span><span class="sxs-lookup"><span data-stu-id="baadb-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baadb-104">语法</span><span class="sxs-lookup"><span data-stu-id="baadb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baadb-105">参数</span><span class="sxs-lookup"><span data-stu-id="baadb-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="baadb-106">弄一个指针，指向设置断点的函数的地址。</span><span class="sxs-lookup"><span data-stu-id="baadb-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baadb-107">要求</span><span class="sxs-lookup"><span data-stu-id="baadb-107">Requirements</span></span>  
 <span data-ttu-id="baadb-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="baadb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baadb-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="baadb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baadb-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baadb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baadb-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baadb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
