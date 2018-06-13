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
ms.openlocfilehash: 2881b1f420d8e177e093969b2cdd9f2ff36883f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412510"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="e011e-102">ICorDebugFunction::CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="e011e-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="e011e-103">此函数的开始处创建断点。</span><span class="sxs-lookup"><span data-stu-id="e011e-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e011e-104">语法</span><span class="sxs-lookup"><span data-stu-id="e011e-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e011e-105">参数</span><span class="sxs-lookup"><span data-stu-id="e011e-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="e011e-106">[out]指向一个表示新函数断点 ICorDebugFunctionBreakpoint 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="e011e-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e011e-107">要求</span><span class="sxs-lookup"><span data-stu-id="e011e-107">Requirements</span></span>  
 <span data-ttu-id="e011e-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e011e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e011e-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e011e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e011e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e011e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e011e-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e011e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
