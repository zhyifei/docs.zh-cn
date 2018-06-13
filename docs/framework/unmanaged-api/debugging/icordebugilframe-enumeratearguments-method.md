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
ms.openlocfilehash: 2e4a727dcfbc80b131f526a08b00bd0ec91ca209
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415017"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="48c0b-102">ICorDebugILFrame::EnumerateArguments 方法</span><span class="sxs-lookup"><span data-stu-id="48c0b-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="48c0b-103">此帧中获取自变量的枚举数。</span><span class="sxs-lookup"><span data-stu-id="48c0b-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48c0b-104">语法</span><span class="sxs-lookup"><span data-stu-id="48c0b-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48c0b-105">参数</span><span class="sxs-lookup"><span data-stu-id="48c0b-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="48c0b-106">[out]指向的地址是此帧中的自变量的枚举器的 ICorDebugValueEnum 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="48c0b-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48c0b-107">备注</span><span class="sxs-lookup"><span data-stu-id="48c0b-107">Remarks</span></span>  
 <span data-ttu-id="48c0b-108">`EnumerateArguments` 获取枚举数，可以列出此 ICorDebugILFrame 对象表示的调用帧中可用的自变量。</span><span class="sxs-lookup"><span data-stu-id="48c0b-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="48c0b-109">列表中会包含由自变量[vararg](/cpp/windows/vararg) （即，数目可变的参数） 不是自变量以及`vararg`。</span><span class="sxs-lookup"><span data-stu-id="48c0b-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48c0b-110">要求</span><span class="sxs-lookup"><span data-stu-id="48c0b-110">Requirements</span></span>  
 <span data-ttu-id="48c0b-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48c0b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48c0b-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48c0b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48c0b-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48c0b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48c0b-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48c0b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
