---
title: ICorDebugProcess2::SetUnmanagedBreakpoint 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178647"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="3549e-102">ICorDebugProcess2::SetUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="3549e-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="3549e-103">在指定的本机图像偏移处设置非托管断点。</span><span class="sxs-lookup"><span data-stu-id="3549e-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3549e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3549e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3549e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="3549e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="3549e-106">[在]`CORDB_ADDRESS`指定本机图像偏移的对象。</span><span class="sxs-lookup"><span data-stu-id="3549e-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="3549e-107">[在]`buffer`数组的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="3549e-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="3549e-108">[出]包含由断点替换的运算码的数组。</span><span class="sxs-lookup"><span data-stu-id="3549e-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="3549e-109">[出]指向数组中返回的字节数的`buffer`指针。</span><span class="sxs-lookup"><span data-stu-id="3549e-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3549e-110">备注</span><span class="sxs-lookup"><span data-stu-id="3549e-110">Remarks</span></span>  
 <span data-ttu-id="3549e-111">如果本机图像偏移在通用语言运行时 （CLR） 内，则断点将被忽略。</span><span class="sxs-lookup"><span data-stu-id="3549e-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="3549e-112">这允许 CLR 避免调度带外断点，当断点由调试器设置时。</span><span class="sxs-lookup"><span data-stu-id="3549e-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3549e-113">要求</span><span class="sxs-lookup"><span data-stu-id="3549e-113">Requirements</span></span>  
 <span data-ttu-id="3549e-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3549e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3549e-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3549e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3549e-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3549e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3549e-117">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3549e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
