---
title: ICorDebugILFrame::GetLocalVariable 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3424646337c3f90f15d991f3f669a296bf11d8ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413002"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="90961-102">ICorDebugILFrame::GetLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="90961-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="90961-103">此 Microsoft 中间语言 (MSIL) 堆栈帧中获取指定的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="90961-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90961-104">语法</span><span class="sxs-lookup"><span data-stu-id="90961-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90961-105">参数</span><span class="sxs-lookup"><span data-stu-id="90961-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="90961-106">[in]此 MSIL 堆栈帧中局部变量的索引。</span><span class="sxs-lookup"><span data-stu-id="90961-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="90961-107">[out]指向一个 ICorDebugValue 对象，表示检索到的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="90961-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90961-108">备注</span><span class="sxs-lookup"><span data-stu-id="90961-108">Remarks</span></span>  
 <span data-ttu-id="90961-109">`GetLocalVariable` MSIL 堆栈帧中或实时 (JIT) 编译框架中，可以使用方法。</span><span class="sxs-lookup"><span data-stu-id="90961-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90961-110">要求</span><span class="sxs-lookup"><span data-stu-id="90961-110">Requirements</span></span>  
 <span data-ttu-id="90961-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90961-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90961-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90961-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90961-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90961-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90961-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90961-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
