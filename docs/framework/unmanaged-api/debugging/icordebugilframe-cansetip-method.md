---
title: ICorDebugILFrame::CanSetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: c6a02b080739d00667893008be4a19b4fa9a6ef2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788595"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="48e50-102">ICorDebugILFrame::CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="48e50-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="48e50-103">获取 HRESULT，它指示在 Microsoft 中间语言（MSIL）代码中将指令指针设置为指定的偏移位置是安全的。</span><span class="sxs-lookup"><span data-stu-id="48e50-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48e50-104">语法</span><span class="sxs-lookup"><span data-stu-id="48e50-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48e50-105">参数</span><span class="sxs-lookup"><span data-stu-id="48e50-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="48e50-106">中指令指针所需的设置。</span><span class="sxs-lookup"><span data-stu-id="48e50-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48e50-107">备注</span><span class="sxs-lookup"><span data-stu-id="48e50-107">Remarks</span></span>  
 <span data-ttu-id="48e50-108">在调用[ICorDebugILFrame：： SetIP](icordebugilframe-setip-method.md)方法之前，请使用 `CanSetIP` 方法。</span><span class="sxs-lookup"><span data-stu-id="48e50-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="48e50-109">如果 `CanSetIP` 返回除 S_OK 以外的任何 HRESULT，则仍可调用 `ICorDebugILFrame::SetIP`，但不保证调试器将继续安全且正确地执行正在调试的代码。</span><span class="sxs-lookup"><span data-stu-id="48e50-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48e50-110">需求</span><span class="sxs-lookup"><span data-stu-id="48e50-110">Requirements</span></span>  
 <span data-ttu-id="48e50-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48e50-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48e50-112">**标头：** Cordebug.idl、Cordebug.idl、h</span><span class="sxs-lookup"><span data-stu-id="48e50-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="48e50-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48e50-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48e50-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48e50-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
