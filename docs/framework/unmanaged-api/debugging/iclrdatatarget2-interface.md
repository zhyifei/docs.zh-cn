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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104710"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="9a9a8-102">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="9a9a8-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="9a9a8-103">子类[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)数据访问服务层使用，以处理目标进程中的虚拟内存区域。</span><span class="sxs-lookup"><span data-stu-id="9a9a8-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a9a8-104">方法</span><span class="sxs-lookup"><span data-stu-id="9a9a8-104">Methods</span></span>  
  
|<span data-ttu-id="9a9a8-105">方法</span><span class="sxs-lookup"><span data-stu-id="9a9a8-105">Method</span></span>|<span data-ttu-id="9a9a8-106">描述</span><span class="sxs-lookup"><span data-stu-id="9a9a8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a9a8-107">AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="9a9a8-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="9a9a8-108">分配目标进程的地址空间中的内存。</span><span class="sxs-lookup"><span data-stu-id="9a9a8-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="9a9a8-109">FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="9a9a8-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="9a9a8-110">释放以前分配的目标进程的地址空间中的内存。</span><span class="sxs-lookup"><span data-stu-id="9a9a8-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a9a8-111">备注</span><span class="sxs-lookup"><span data-stu-id="9a9a8-111">Remarks</span></span>  
 <span data-ttu-id="9a9a8-112">API 客户端（即调试器）必须针对特定的目标进程实现此接口。</span><span class="sxs-lookup"><span data-stu-id="9a9a8-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="9a9a8-113">例如，活动进程的实现将不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="9a9a8-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="9a9a8-114">目标可能不支持对其内存区域的修改。</span><span class="sxs-lookup"><span data-stu-id="9a9a8-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a9a8-115">要求</span><span class="sxs-lookup"><span data-stu-id="9a9a8-115">Requirements</span></span>  
 <span data-ttu-id="9a9a8-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9a9a8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a9a8-117">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="9a9a8-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9a9a8-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a9a8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a9a8-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a9a8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a9a8-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a9a8-120">See also</span></span>

- [<span data-ttu-id="9a9a8-121">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="9a9a8-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="9a9a8-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="9a9a8-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
