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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695ce7f25813a191c74bec6563fc7f8ae8d1143d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496113"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="73ff5-102">ICorDebugFunction::CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="73ff5-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="73ff5-103">此函数的开始处创建断点。</span><span class="sxs-lookup"><span data-stu-id="73ff5-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73ff5-104">语法</span><span class="sxs-lookup"><span data-stu-id="73ff5-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73ff5-105">参数</span><span class="sxs-lookup"><span data-stu-id="73ff5-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="73ff5-106">[out]指向一个 ICorDebugFunctionBreakpoint 对象，表示新断点的函数的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="73ff5-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73ff5-107">要求</span><span class="sxs-lookup"><span data-stu-id="73ff5-107">Requirements</span></span>  
 <span data-ttu-id="73ff5-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73ff5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73ff5-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73ff5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73ff5-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73ff5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73ff5-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73ff5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
