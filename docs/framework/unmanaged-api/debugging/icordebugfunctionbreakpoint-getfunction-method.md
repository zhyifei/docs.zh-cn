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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da22570441324a01fea307116bc23601e62919a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411359"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="7e929-102">ICorDebugFunctionBreakpoint::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="7e929-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="7e929-103">引用在其中设置断点的函数 ICorDebugFunction 获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="7e929-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e929-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e929-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e929-105">参数</span><span class="sxs-lookup"><span data-stu-id="7e929-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="7e929-106">[out]指向在其中设置断点的函数的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="7e929-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e929-107">要求</span><span class="sxs-lookup"><span data-stu-id="7e929-107">Requirements</span></span>  
 <span data-ttu-id="7e929-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e929-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e929-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e929-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e929-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e929-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e929-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e929-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
