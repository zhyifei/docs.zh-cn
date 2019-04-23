---
title: ICorDebugProcess6::DecodeEvent 方法
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a392e236f180771a9b05526a0db569f27f6f7d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230741"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="28b08-102">ICorDebugProcess6::DecodeEvent 方法</span><span class="sxs-lookup"><span data-stu-id="28b08-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="28b08-103">对封装于特殊构造的本机异常调试事件有效载荷中的托管调试事件进行解码。</span><span class="sxs-lookup"><span data-stu-id="28b08-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28b08-104">语法</span><span class="sxs-lookup"><span data-stu-id="28b08-104">Syntax</span></span>  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28b08-105">参数</span><span class="sxs-lookup"><span data-stu-id="28b08-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="28b08-106">[输入] 包含托管调试事件相关信息的本机异常调试事件中的字节数组指针。</span><span class="sxs-lookup"><span data-stu-id="28b08-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="28b08-107">[输入] `pRecord` 字节数组中的元素数量。</span><span class="sxs-lookup"><span data-stu-id="28b08-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="28b08-108">[in]一个[CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)枚举成员，指定的非托管的调试事件格式。</span><span class="sxs-lookup"><span data-stu-id="28b08-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="28b08-109">[输入] 位域依赖于目标体系结构并指定调试事件相关的其他信息。</span><span class="sxs-lookup"><span data-stu-id="28b08-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="28b08-110">对于 Windows 系统，它可以是的成员[CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="28b08-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="28b08-111">[输入] 引发异常的线程的操作系统识别符。</span><span class="sxs-lookup"><span data-stu-id="28b08-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="28b08-112">[out]指向的地址的指针[icor 调试调试事件](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)对象，表示已解码托管的调试事件。</span><span class="sxs-lookup"><span data-stu-id="28b08-112">[out] A pointer to the address of an [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28b08-113">备注</span><span class="sxs-lookup"><span data-stu-id="28b08-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28b08-114">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="28b08-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28b08-115">要求</span><span class="sxs-lookup"><span data-stu-id="28b08-115">Requirements</span></span>  
 <span data-ttu-id="28b08-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28b08-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28b08-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28b08-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28b08-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28b08-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28b08-119">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28b08-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28b08-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="28b08-120">See also</span></span>

- [<span data-ttu-id="28b08-121">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="28b08-121">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="28b08-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="28b08-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
