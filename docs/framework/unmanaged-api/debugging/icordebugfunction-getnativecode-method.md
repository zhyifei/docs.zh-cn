---
title: ICorDebugFunction::GetNativeCode 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb85c4b2c26c136a5f9fc05221a42c4bc99f37f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988697"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="729b4-102">ICorDebugFunction::GetNativeCode 方法</span><span class="sxs-lookup"><span data-stu-id="729b4-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="729b4-103">获取此 ICorDebugFunction 实例所表示的函数的本机代码。</span><span class="sxs-lookup"><span data-stu-id="729b4-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="729b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="729b4-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="729b4-105">参数</span><span class="sxs-lookup"><span data-stu-id="729b4-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="729b4-106">[out]指向表示此函数，或者都为 null 的本机代码，如果此函数是尚未实时 (JIT) 编译的 Microsoft 中间语言 (MSIL) 代码的 ICorDebugCode 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="729b4-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="729b4-107">备注</span><span class="sxs-lookup"><span data-stu-id="729b4-107">Remarks</span></span>  
 <span data-ttu-id="729b4-108">如果由此函数`ICorDebugFunction`实例已 JIT 编译一次以上，对于泛型类型，如`GetNativeCode`返回随机的本机代码对象。</span><span class="sxs-lookup"><span data-stu-id="729b4-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="729b4-109">要求</span><span class="sxs-lookup"><span data-stu-id="729b4-109">Requirements</span></span>  
 <span data-ttu-id="729b4-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="729b4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="729b4-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="729b4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="729b4-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="729b4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="729b4-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="729b4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
