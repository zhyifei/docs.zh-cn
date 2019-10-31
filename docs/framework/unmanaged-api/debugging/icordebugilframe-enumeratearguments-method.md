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
ms.openlocfilehash: d74c5a6f966201c8ca9d2854de2e9986e7f1d0fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131028"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="4fb19-102">ICorDebugILFrame::EnumerateArguments 方法</span><span class="sxs-lookup"><span data-stu-id="4fb19-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="4fb19-103">获取此帧中的参数的枚举数。</span><span class="sxs-lookup"><span data-stu-id="4fb19-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb19-104">语法</span><span class="sxs-lookup"><span data-stu-id="4fb19-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fb19-105">参数</span><span class="sxs-lookup"><span data-stu-id="4fb19-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="4fb19-106">弄指向 ICorDebugValueEnum 对象地址的指针，该对象是此帧中自变量的枚举器。</span><span class="sxs-lookup"><span data-stu-id="4fb19-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fb19-107">备注</span><span class="sxs-lookup"><span data-stu-id="4fb19-107">Remarks</span></span>  
 <span data-ttu-id="4fb19-108">`EnumerateArguments` 获取一个枚举器，该枚举数可以列出此 ICorDebugILFrame 对象所表示的调用帧中可用的参数。</span><span class="sxs-lookup"><span data-stu-id="4fb19-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="4fb19-109">此列表将包含[vararg](/cpp/windows/vararg)参数（即可变数量的参数）以及不 `vararg`的参数。</span><span class="sxs-lookup"><span data-stu-id="4fb19-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fb19-110">要求</span><span class="sxs-lookup"><span data-stu-id="4fb19-110">Requirements</span></span>  
 <span data-ttu-id="4fb19-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb19-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fb19-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fb19-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fb19-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fb19-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fb19-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fb19-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
