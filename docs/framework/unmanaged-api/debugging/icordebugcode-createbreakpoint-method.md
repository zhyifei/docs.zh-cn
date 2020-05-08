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
ms.openlocfilehash: 40582b1289875d5151ea96e3153c6e4760737e84
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893810"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="3e71f-102">ICorDebugCode::CreateBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="3e71f-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="3e71f-103">在此代码段中的指定偏移量处创建断点。</span><span class="sxs-lookup"><span data-stu-id="3e71f-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e71f-104">语法</span><span class="sxs-lookup"><span data-stu-id="3e71f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e71f-105">参数</span><span class="sxs-lookup"><span data-stu-id="3e71f-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="3e71f-106">中创建断点的偏移量。</span><span class="sxs-lookup"><span data-stu-id="3e71f-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="3e71f-107">弄指向表示断点的 "ICorDebugFunctionBreakpoint" 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3e71f-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e71f-108">备注</span><span class="sxs-lookup"><span data-stu-id="3e71f-108">Remarks</span></span>  
 <span data-ttu-id="3e71f-109">在断点处于活动状态之前，必须将其添加到进程对象。</span><span class="sxs-lookup"><span data-stu-id="3e71f-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="3e71f-110">如果此代码为 Microsoft 中间语言（MSIL）代码，并且有一个实时（JIT）编译的本机版本的代码，则将在 JIT 编译的代码中应用该断点。</span><span class="sxs-lookup"><span data-stu-id="3e71f-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="3e71f-111">（如果以后 JIT 编译代码，则也是如此。）</span><span class="sxs-lookup"><span data-stu-id="3e71f-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e71f-112">要求</span><span class="sxs-lookup"><span data-stu-id="3e71f-112">Requirements</span></span>  
 <span data-ttu-id="3e71f-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e71f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e71f-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e71f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e71f-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e71f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e71f-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e71f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
