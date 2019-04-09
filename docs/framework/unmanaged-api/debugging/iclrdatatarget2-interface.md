---
title: ICLRDataTarget2 接口
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d21bced214242866c47f40f392593f3f51cda02f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104710"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="527cd-102">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="527cd-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="527cd-103">子类[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)数据访问服务层使用，以处理目标进程中的虚拟内存区域。</span><span class="sxs-lookup"><span data-stu-id="527cd-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="527cd-104">方法</span><span class="sxs-lookup"><span data-stu-id="527cd-104">Methods</span></span>  
  
|<span data-ttu-id="527cd-105">方法</span><span class="sxs-lookup"><span data-stu-id="527cd-105">Method</span></span>|<span data-ttu-id="527cd-106">描述</span><span class="sxs-lookup"><span data-stu-id="527cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="527cd-107">AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="527cd-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="527cd-108">分配目标进程的地址空间中的内存。</span><span class="sxs-lookup"><span data-stu-id="527cd-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="527cd-109">FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="527cd-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="527cd-110">释放以前分配的目标进程的地址空间中的内存。</span><span class="sxs-lookup"><span data-stu-id="527cd-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="527cd-111">备注</span><span class="sxs-lookup"><span data-stu-id="527cd-111">Remarks</span></span>  
 <span data-ttu-id="527cd-112">API 客户端（即调试器）必须针对特定的目标进程实现此接口。</span><span class="sxs-lookup"><span data-stu-id="527cd-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="527cd-113">例如，活动进程的实现将不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="527cd-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="527cd-114">目标可能不支持对其内存区域的修改。</span><span class="sxs-lookup"><span data-stu-id="527cd-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="527cd-115">要求</span><span class="sxs-lookup"><span data-stu-id="527cd-115">Requirements</span></span>  
 <span data-ttu-id="527cd-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="527cd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="527cd-117">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="527cd-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="527cd-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="527cd-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="527cd-119">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="527cd-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="527cd-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="527cd-120">See also</span></span>

- [<span data-ttu-id="527cd-121">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="527cd-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="527cd-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="527cd-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
