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
ms.openlocfilehash: c18f2fce23e979f27d9116e74b6c6b007cd33bf0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752884"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="4c7df-102">ICorDebugILFrame::EnumerateLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="4c7df-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="4c7df-103">获取在此帧中局部变量的枚举数。</span><span class="sxs-lookup"><span data-stu-id="4c7df-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c7df-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c7df-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c7df-105">参数</span><span class="sxs-lookup"><span data-stu-id="4c7df-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="4c7df-106">[out]指向一个 ICorDebugValueEnum 对象，它在此帧中局部变量的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4c7df-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c7df-107">备注</span><span class="sxs-lookup"><span data-stu-id="4c7df-107">Remarks</span></span>  
 <span data-ttu-id="4c7df-108">`EnumerateLocalVariables` 获取可以列出可用由此 ICorDebugILFrame 对象的调用帧中局部变量的枚举器。</span><span class="sxs-lookup"><span data-stu-id="4c7df-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="4c7df-109">列表可能不包括的所有本地变量在正在运行的函数中，因为其中一些可能未处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="4c7df-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c7df-110">要求</span><span class="sxs-lookup"><span data-stu-id="4c7df-110">Requirements</span></span>  
 <span data-ttu-id="4c7df-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c7df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c7df-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c7df-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c7df-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c7df-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c7df-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c7df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
