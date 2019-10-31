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
ms.openlocfilehash: 1f0f4331302e56a90b4aefd657e07981994022ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112317"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="457db-102">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="457db-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="457db-103">数据访问服务层用于处理目标进程中的虚拟内存区域的[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)的子类。</span><span class="sxs-lookup"><span data-stu-id="457db-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="457db-104">方法</span><span class="sxs-lookup"><span data-stu-id="457db-104">Methods</span></span>  
  
|<span data-ttu-id="457db-105">方法</span><span class="sxs-lookup"><span data-stu-id="457db-105">Method</span></span>|<span data-ttu-id="457db-106">描述</span><span class="sxs-lookup"><span data-stu-id="457db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="457db-107">AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="457db-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="457db-108">在目标进程的地址空间中分配内存。</span><span class="sxs-lookup"><span data-stu-id="457db-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="457db-109">FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="457db-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="457db-110">释放以前在目标进程的地址空间中分配的内存。</span><span class="sxs-lookup"><span data-stu-id="457db-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="457db-111">备注</span><span class="sxs-lookup"><span data-stu-id="457db-111">Remarks</span></span>  
 <span data-ttu-id="457db-112">API 客户端（即调试器）必须针对特定的目标进程实现此接口。</span><span class="sxs-lookup"><span data-stu-id="457db-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="457db-113">例如，活动进程的实现将不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="457db-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="457db-114">目标可能不支持对其内存区域的修改。</span><span class="sxs-lookup"><span data-stu-id="457db-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="457db-115">要求</span><span class="sxs-lookup"><span data-stu-id="457db-115">Requirements</span></span>  
 <span data-ttu-id="457db-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="457db-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="457db-117">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="457db-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="457db-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="457db-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="457db-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="457db-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457db-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="457db-120">See also</span></span>

- [<span data-ttu-id="457db-121">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="457db-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="457db-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="457db-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
