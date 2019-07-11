---
title: ICorDebugILFrame::EnumerateArguments 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 499f58cc0a3f2d1b3c159435ed7d9b523f25e29e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757889"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="4da73-102">ICorDebugILFrame::EnumerateArguments 方法</span><span class="sxs-lookup"><span data-stu-id="4da73-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="4da73-103">在此范围内的自变量中获取一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="4da73-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da73-104">语法</span><span class="sxs-lookup"><span data-stu-id="4da73-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4da73-105">参数</span><span class="sxs-lookup"><span data-stu-id="4da73-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="4da73-106">[out]指向一个 ICorDebugValueEnum 对象，它在此范围内的自变量枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4da73-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4da73-107">备注</span><span class="sxs-lookup"><span data-stu-id="4da73-107">Remarks</span></span>  
 <span data-ttu-id="4da73-108">`EnumerateArguments` 获取可以列出由此 ICorDebugILFrame 对象调用框架中提供的参数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="4da73-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="4da73-109">该列表将包括参数是[vararg](/cpp/windows/vararg) （即，可变自变量的数量） 以及参数不是`vararg`。</span><span class="sxs-lookup"><span data-stu-id="4da73-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4da73-110">要求</span><span class="sxs-lookup"><span data-stu-id="4da73-110">Requirements</span></span>  
 <span data-ttu-id="4da73-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4da73-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4da73-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4da73-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4da73-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4da73-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4da73-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4da73-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
