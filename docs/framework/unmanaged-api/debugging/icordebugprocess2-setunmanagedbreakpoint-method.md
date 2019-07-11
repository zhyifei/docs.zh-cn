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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f16a5d1bad80a5aad8573508aab5fbf98c8c2a03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736834"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="faca7-102">ICorDebugProcess2::SetUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="faca7-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="faca7-103">设置指定的本机映像的偏移量处的非托管的断点。</span><span class="sxs-lookup"><span data-stu-id="faca7-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faca7-104">语法</span><span class="sxs-lookup"><span data-stu-id="faca7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faca7-105">参数</span><span class="sxs-lookup"><span data-stu-id="faca7-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="faca7-106">[in]一个`CORDB_ADDRESS`对象，它指定的本机映像偏移量。</span><span class="sxs-lookup"><span data-stu-id="faca7-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="faca7-107">[in]大小，以字节为单位的`buffer`数组。</span><span class="sxs-lookup"><span data-stu-id="faca7-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="faca7-108">[out]一个数组，包含被替换为该断点的操作码。</span><span class="sxs-lookup"><span data-stu-id="faca7-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="faca7-109">[out]指向中返回的字节数的`buffer`数组。</span><span class="sxs-lookup"><span data-stu-id="faca7-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faca7-110">备注</span><span class="sxs-lookup"><span data-stu-id="faca7-110">Remarks</span></span>  
 <span data-ttu-id="faca7-111">如果本机映像偏移量为公共语言运行时 (CLR) 中，断点将被忽略。</span><span class="sxs-lookup"><span data-stu-id="faca7-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="faca7-112">这样可使 CLR 以避免调度的带断点时调试器设置断点。</span><span class="sxs-lookup"><span data-stu-id="faca7-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faca7-113">要求</span><span class="sxs-lookup"><span data-stu-id="faca7-113">Requirements</span></span>  
 <span data-ttu-id="faca7-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="faca7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faca7-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faca7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faca7-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faca7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faca7-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faca7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
