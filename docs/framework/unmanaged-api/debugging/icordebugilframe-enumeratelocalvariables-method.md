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
ms.openlocfilehash: c071a7ddb7d8d3f0e6487ab85284c45f9a7f0372
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178844"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="a6f8e-102">ICorDebugILFrame::EnumerateLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="a6f8e-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="a6f8e-103">获取此帧中局部变量的枚举器。</span><span class="sxs-lookup"><span data-stu-id="a6f8e-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6f8e-104">语法</span><span class="sxs-lookup"><span data-stu-id="a6f8e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6f8e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="a6f8e-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="a6f8e-106">[out] 一个指向 ICorDebugValueEnum 对象的地址的指针，该对象是此帧中局部变量的枚举器。</span><span class="sxs-lookup"><span data-stu-id="a6f8e-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6f8e-107">备注</span><span class="sxs-lookup"><span data-stu-id="a6f8e-107">Remarks</span></span>  
 <span data-ttu-id="a6f8e-108">`EnumerateLocalVariables`获取一个枚举器，该枚举器可以列出此 ICorDebugILFrame 对象表示的调用帧中可用的局部变量。</span><span class="sxs-lookup"><span data-stu-id="a6f8e-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="a6f8e-109">该列表可能不包括正在运行的函数中的所有局部变量，因为其中一些变量可能未处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a6f8e-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6f8e-110">要求</span><span class="sxs-lookup"><span data-stu-id="a6f8e-110">Requirements</span></span>  
 <span data-ttu-id="a6f8e-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f8e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f8e-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6f8e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6f8e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6f8e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6f8e-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f8e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
