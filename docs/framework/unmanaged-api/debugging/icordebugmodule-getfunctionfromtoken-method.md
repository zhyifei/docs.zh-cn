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
ms.openlocfilehash: cb966a918c63b4fbc00dcf52819b9384427dfdaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129590"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="475c5-102">ICorDebugModule::GetFunctionFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="475c5-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="475c5-103">获取元数据标记指定的函数。</span><span class="sxs-lookup"><span data-stu-id="475c5-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="475c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="475c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="475c5-105">参数</span><span class="sxs-lookup"><span data-stu-id="475c5-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="475c5-106">中引用函数的元数据的 `mdMethodDef` 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="475c5-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="475c5-107">弄指向表示函数的 ICorDebugFunction 接口对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="475c5-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="475c5-108">备注</span><span class="sxs-lookup"><span data-stu-id="475c5-108">Remarks</span></span>  
 <span data-ttu-id="475c5-109">如果 `methodDef` 中传递的值不引用 Microsoft 中间语言（MSIL）方法，`GetFunctionFromToken` 方法将返回 CORDBG_E_FUNCTION_NOT_IL HRESULT。</span><span class="sxs-lookup"><span data-stu-id="475c5-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="475c5-110">要求</span><span class="sxs-lookup"><span data-stu-id="475c5-110">Requirements</span></span>  
 <span data-ttu-id="475c5-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="475c5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="475c5-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="475c5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="475c5-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="475c5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="475c5-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="475c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
