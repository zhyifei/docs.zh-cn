---
title: ICorDebugModule::GetFunctionFromToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1af0f8f792c856c0b27b4d3d9ff557bcc5fce82
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500065"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="af47e-102">ICorDebugModule::GetFunctionFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="af47e-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="af47e-103">获取指定的元数据标记的函数。</span><span class="sxs-lookup"><span data-stu-id="af47e-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af47e-104">语法</span><span class="sxs-lookup"><span data-stu-id="af47e-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af47e-105">参数</span><span class="sxs-lookup"><span data-stu-id="af47e-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="af47e-106">[in]一个`mdMethodDef`元数据标记所引用的函数的元数据。</span><span class="sxs-lookup"><span data-stu-id="af47e-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="af47e-107">[out]ICorDebugFunction 接口对象，表示该函数的地址指针。</span><span class="sxs-lookup"><span data-stu-id="af47e-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af47e-108">备注</span><span class="sxs-lookup"><span data-stu-id="af47e-108">Remarks</span></span>  
 <span data-ttu-id="af47e-109">`GetFunctionFromToken`如果中传递的值，方法将返回 CORDBG_E_FUNCTION_NOT_IL HRESULT`methodDef`不引用 Microsoft 中间语言 (MSIL) 方法。</span><span class="sxs-lookup"><span data-stu-id="af47e-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af47e-110">要求</span><span class="sxs-lookup"><span data-stu-id="af47e-110">Requirements</span></span>  
 <span data-ttu-id="af47e-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af47e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af47e-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af47e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af47e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af47e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af47e-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af47e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
