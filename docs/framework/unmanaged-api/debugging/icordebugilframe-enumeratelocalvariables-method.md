---
title: ICorDebugILFrame::EnumerateLocalVariables 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cc9601105d05740e6db0a41bae521bd9a276d74
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471311"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="b5223-102">ICorDebugILFrame::EnumerateLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="b5223-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="b5223-103">获取在此帧中局部变量的枚举数。</span><span class="sxs-lookup"><span data-stu-id="b5223-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5223-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5223-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5223-105">参数</span><span class="sxs-lookup"><span data-stu-id="b5223-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="b5223-106">[out]指向一个 ICorDebugValueEnum 对象，它在此帧中局部变量的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b5223-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5223-107">备注</span><span class="sxs-lookup"><span data-stu-id="b5223-107">Remarks</span></span>  
 <span data-ttu-id="b5223-108">`EnumerateLocalVariables` 获取可以列出可用由此 ICorDebugILFrame 对象的调用帧中局部变量的枚举器。</span><span class="sxs-lookup"><span data-stu-id="b5223-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="b5223-109">列表可能不包括的所有本地变量在正在运行的函数中，因为其中一些可能未处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b5223-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5223-110">要求</span><span class="sxs-lookup"><span data-stu-id="b5223-110">Requirements</span></span>  
 <span data-ttu-id="b5223-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5223-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5223-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5223-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5223-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5223-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5223-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5223-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
