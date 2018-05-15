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
ms.openlocfilehash: d4326c6d8a3ee780cf63652badc8c527f55a075c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="738de-102">ICorDebugProcess2::SetUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="738de-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="738de-103">指定的本机映像的偏移量处设置非托管的断点。</span><span class="sxs-lookup"><span data-stu-id="738de-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="738de-104">语法</span><span class="sxs-lookup"><span data-stu-id="738de-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="738de-105">参数</span><span class="sxs-lookup"><span data-stu-id="738de-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="738de-106">[in]A`CORDB_ADDRESS`对象，它指定的本机映像偏移量。</span><span class="sxs-lookup"><span data-stu-id="738de-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="738de-107">[in]大小，以字节为单位的`buffer`数组。</span><span class="sxs-lookup"><span data-stu-id="738de-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="738de-108">[out]一个数组，包含由断点替换操作码。</span><span class="sxs-lookup"><span data-stu-id="738de-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="738de-109">[out]指向返回中的字节数的指针`buffer`数组。</span><span class="sxs-lookup"><span data-stu-id="738de-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="738de-110">备注</span><span class="sxs-lookup"><span data-stu-id="738de-110">Remarks</span></span>  
 <span data-ttu-id="738de-111">如果公共语言运行时 (CLR) 内的本机映像偏移量，则将忽略断点。</span><span class="sxs-lookup"><span data-stu-id="738de-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="738de-112">这样，以避免断点设置由调试器时调度带的断点，CLR。</span><span class="sxs-lookup"><span data-stu-id="738de-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="738de-113">要求</span><span class="sxs-lookup"><span data-stu-id="738de-113">Requirements</span></span>  
 <span data-ttu-id="738de-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="738de-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="738de-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="738de-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="738de-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="738de-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="738de-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="738de-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
