---
title: ICorDebugFunction::CreateBreakpoint 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
ms.openlocfilehash: 64304b671532325bdc2f8841a2702d537d143330
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124042"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="b648b-102">ICorDebugFunction::CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="b648b-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="b648b-103">在此函数的开头创建一个断点。</span><span class="sxs-lookup"><span data-stu-id="b648b-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b648b-104">语法</span><span class="sxs-lookup"><span data-stu-id="b648b-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b648b-105">参数</span><span class="sxs-lookup"><span data-stu-id="b648b-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="b648b-106">弄指向 ICorDebugFunctionBreakpoint 对象的地址的指针，该对象表示函数的新断点。</span><span class="sxs-lookup"><span data-stu-id="b648b-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b648b-107">要求</span><span class="sxs-lookup"><span data-stu-id="b648b-107">Requirements</span></span>  
 <span data-ttu-id="b648b-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b648b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b648b-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b648b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b648b-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b648b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b648b-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b648b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
