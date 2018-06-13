---
title: ICorDebugFunctionBreakpoint::GetOffset 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aca1d77ace512ca84cda3b6844d214e4c8d6cad7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412060"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="d6e3b-102">ICorDebugFunctionBreakpoint::GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="d6e3b-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>
<span data-ttu-id="d6e3b-103">获取断点在函数中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="d6e3b-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e3b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6e3b-104">Syntax</span></span>  
  
```  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6e3b-105">参数</span><span class="sxs-lookup"><span data-stu-id="d6e3b-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="d6e3b-106">[out]指向断点的偏移量的指针。</span><span class="sxs-lookup"><span data-stu-id="d6e3b-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6e3b-107">要求</span><span class="sxs-lookup"><span data-stu-id="d6e3b-107">Requirements</span></span>  
 <span data-ttu-id="d6e3b-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6e3b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e3b-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6e3b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6e3b-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6e3b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6e3b-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6e3b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
