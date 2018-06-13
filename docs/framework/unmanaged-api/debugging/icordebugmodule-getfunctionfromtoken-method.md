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
ms.openlocfilehash: acffd24ae9d5aad5f48058eec036f912ee016289
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415979"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="56439-102">ICorDebugModule::GetFunctionFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="56439-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="56439-103">获取指定元数据标记的函数。</span><span class="sxs-lookup"><span data-stu-id="56439-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56439-104">语法</span><span class="sxs-lookup"><span data-stu-id="56439-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56439-105">参数</span><span class="sxs-lookup"><span data-stu-id="56439-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="56439-106">[in]A`mdMethodDef`引用函数的元数据的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="56439-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="56439-107">[out]指向表示的函数的 ICorDebugFunction 接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="56439-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56439-108">备注</span><span class="sxs-lookup"><span data-stu-id="56439-108">Remarks</span></span>  
 <span data-ttu-id="56439-109">`GetFunctionFromToken`如果中传递的值，方法将返回 CORDBG_E_FUNCTION_NOT_IL HRESULT`methodDef`未引用 Microsoft 中间语言 (MSIL) 方法。</span><span class="sxs-lookup"><span data-stu-id="56439-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56439-110">要求</span><span class="sxs-lookup"><span data-stu-id="56439-110">Requirements</span></span>  
 <span data-ttu-id="56439-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="56439-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56439-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56439-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56439-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56439-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56439-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56439-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
