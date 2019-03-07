---
title: ICorDebugCode::CreateBreakpoint 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df27d2ab609551bb7a7f6f4b0ff8c7118c9f93f8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478669"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="73308-102">ICorDebugCode::CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="73308-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="73308-103">在此代码段中指定的偏移量位置处创建断点。</span><span class="sxs-lookup"><span data-stu-id="73308-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73308-104">语法</span><span class="sxs-lookup"><span data-stu-id="73308-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73308-105">参数</span><span class="sxs-lookup"><span data-stu-id="73308-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="73308-106">[in]从其创建断点的偏移量。</span><span class="sxs-lookup"><span data-stu-id="73308-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="73308-107">[out]指向一个"ICorDebugFunctionBreakpoint"对象，表示该断点的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="73308-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73308-108">备注</span><span class="sxs-lookup"><span data-stu-id="73308-108">Remarks</span></span>  
 <span data-ttu-id="73308-109">断点处于活动状态之前，必须添加到的进程对象。</span><span class="sxs-lookup"><span data-stu-id="73308-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="73308-110">如果此代码为 Microsoft 中间语言 (MSIL) 代码，并且没有在实时 (JIT) 的已编译的本机版本的代码，断点将应用中也是 JIT 编译的代码。</span><span class="sxs-lookup"><span data-stu-id="73308-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="73308-111">（这同样适用如果代码为 JIT 编译更高版本。）</span><span class="sxs-lookup"><span data-stu-id="73308-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73308-112">要求</span><span class="sxs-lookup"><span data-stu-id="73308-112">Requirements</span></span>  
 <span data-ttu-id="73308-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73308-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73308-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73308-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73308-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73308-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73308-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73308-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73308-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="73308-117">See also</span></span>

