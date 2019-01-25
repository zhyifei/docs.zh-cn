---
title: ICLRDataTarget3 接口
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 974abb123c4c11f6bb512431cea5cc6460a5c55a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654733"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="e6b0e-102">ICLRDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="e6b0e-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="e6b0e-103">子类[ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)提供对异常信息的访问。</span><span class="sxs-lookup"><span data-stu-id="e6b0e-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6b0e-104">方法</span><span class="sxs-lookup"><span data-stu-id="e6b0e-104">Methods</span></span>  
  
|<span data-ttu-id="e6b0e-105">方法</span><span class="sxs-lookup"><span data-stu-id="e6b0e-105">Method</span></span>|<span data-ttu-id="e6b0e-106">描述</span><span class="sxs-lookup"><span data-stu-id="e6b0e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6b0e-107">GetExceptionRecord 方法</span><span class="sxs-lookup"><span data-stu-id="e6b0e-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="e6b0e-108">由公共语言运行时 (CLR) 数据访问服务调用，以检索与目标进程关联的异常记录。</span><span class="sxs-lookup"><span data-stu-id="e6b0e-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="e6b0e-109">GetExceptionContextRecord 方法</span><span class="sxs-lookup"><span data-stu-id="e6b0e-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="e6b0e-110">由公共语言运行时 (CLR) 数据访问服务调用，以检索与目标进程关联的上下文记录。</span><span class="sxs-lookup"><span data-stu-id="e6b0e-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="e6b0e-111">GetExceptionThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="e6b0e-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="e6b0e-112">由 CLR 数据访问服务调用，从而获取引发异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="e6b0e-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6b0e-113">备注</span><span class="sxs-lookup"><span data-stu-id="e6b0e-113">Remarks</span></span>  
 <span data-ttu-id="e6b0e-114">API 客户端（即调试器）必须针对特定的目标进程实现此接口。</span><span class="sxs-lookup"><span data-stu-id="e6b0e-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="e6b0e-115">例如，活动进程的实现将不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="e6b0e-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="e6b0e-116">目标可能不支持对其内存区域的修改。</span><span class="sxs-lookup"><span data-stu-id="e6b0e-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6b0e-117">要求</span><span class="sxs-lookup"><span data-stu-id="e6b0e-117">Requirements</span></span>  
 <span data-ttu-id="e6b0e-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b0e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6b0e-119">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e6b0e-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e6b0e-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6b0e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6b0e-121">**.NET Framework 版本：**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6b0e-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b0e-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6b0e-122">See also</span></span>
- [<span data-ttu-id="e6b0e-123">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="e6b0e-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="e6b0e-124">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="e6b0e-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="e6b0e-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="e6b0e-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
