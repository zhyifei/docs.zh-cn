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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994859"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="42dd3-102">ICorDebugModule::GetFunctionFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="42dd3-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="42dd3-103">获取指定的元数据标记的函数。</span><span class="sxs-lookup"><span data-stu-id="42dd3-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42dd3-104">语法</span><span class="sxs-lookup"><span data-stu-id="42dd3-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42dd3-105">参数</span><span class="sxs-lookup"><span data-stu-id="42dd3-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="42dd3-106">[in]一个`mdMethodDef`元数据标记所引用的函数的元数据。</span><span class="sxs-lookup"><span data-stu-id="42dd3-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="42dd3-107">[out]ICorDebugFunction 接口对象，表示该函数的地址指针。</span><span class="sxs-lookup"><span data-stu-id="42dd3-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42dd3-108">备注</span><span class="sxs-lookup"><span data-stu-id="42dd3-108">Remarks</span></span>  
 <span data-ttu-id="42dd3-109">`GetFunctionFromToken`如果中传递的值，方法将返回 CORDBG_E_FUNCTION_NOT_IL HRESULT`methodDef`不引用 Microsoft 中间语言 (MSIL) 方法。</span><span class="sxs-lookup"><span data-stu-id="42dd3-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42dd3-110">要求</span><span class="sxs-lookup"><span data-stu-id="42dd3-110">Requirements</span></span>  
 <span data-ttu-id="42dd3-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42dd3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42dd3-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42dd3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42dd3-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42dd3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42dd3-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42dd3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
