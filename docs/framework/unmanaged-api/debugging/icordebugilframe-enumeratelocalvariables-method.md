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
ms.openlocfilehash: ad1a91e42f582ce96906da5cbf00ca89acb18499
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210288"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="647a4-102">ICorDebugILFrame::EnumerateLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="647a4-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="647a4-103">获取此帧中局部变量的枚举数。</span><span class="sxs-lookup"><span data-stu-id="647a4-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="647a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="647a4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="647a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="647a4-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="647a4-106">[out] 一个指向 ICorDebugValueEnum 对象的地址的指针，该对象是此帧中局部变量的枚举器。</span><span class="sxs-lookup"><span data-stu-id="647a4-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="647a4-107">备注</span><span class="sxs-lookup"><span data-stu-id="647a4-107">Remarks</span></span>  
 <span data-ttu-id="647a4-108">`EnumerateLocalVariables`获取一个枚举器，该枚举数可以列出此 ICorDebugILFrame 对象所表示的调用帧中可用的局部变量。</span><span class="sxs-lookup"><span data-stu-id="647a4-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="647a4-109">此列表可能不包括正在运行的函数中的所有局部变量，因为其中一些局部变量可能不处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="647a4-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="647a4-110">要求</span><span class="sxs-lookup"><span data-stu-id="647a4-110">Requirements</span></span>  
 <span data-ttu-id="647a4-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="647a4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="647a4-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="647a4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="647a4-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="647a4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="647a4-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="647a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
