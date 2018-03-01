---
title: "ICLRDataTarget2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8d8dc7aad35e38b2f9d3b5fb48dacbe1d22bd34
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="b1d4a-102">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="b1d4a-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="b1d4a-103">一个子类[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)用于数据访问服务层操作目标进程中的虚拟内存区域。</span><span class="sxs-lookup"><span data-stu-id="b1d4a-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1d4a-104">方法</span><span class="sxs-lookup"><span data-stu-id="b1d4a-104">Methods</span></span>  
  
|<span data-ttu-id="b1d4a-105">方法</span><span class="sxs-lookup"><span data-stu-id="b1d4a-105">Method</span></span>|<span data-ttu-id="b1d4a-106">描述</span><span class="sxs-lookup"><span data-stu-id="b1d4a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1d4a-107">AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="b1d4a-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="b1d4a-108">分配的目标进程地址空间中的内存。</span><span class="sxs-lookup"><span data-stu-id="b1d4a-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="b1d4a-109">FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="b1d4a-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="b1d4a-110">将释放之前已在目标进程的地址空间中分配的内存。</span><span class="sxs-lookup"><span data-stu-id="b1d4a-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1d4a-111">备注</span><span class="sxs-lookup"><span data-stu-id="b1d4a-111">Remarks</span></span>  
 <span data-ttu-id="b1d4a-112">API 客户端（即调试器）必须针对特定的目标进程实现此接口。</span><span class="sxs-lookup"><span data-stu-id="b1d4a-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="b1d4a-113">例如，活动进程的实现将不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="b1d4a-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="b1d4a-114">目标可能不支持对其内存区域的修改。</span><span class="sxs-lookup"><span data-stu-id="b1d4a-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1d4a-115">惠?</span><span class="sxs-lookup"><span data-stu-id="b1d4a-115">Requirements</span></span>  
 <span data-ttu-id="b1d4a-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b1d4a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1d4a-117">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b1d4a-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b1d4a-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1d4a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1d4a-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1d4a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d4a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1d4a-120">See Also</span></span>  
 [<span data-ttu-id="b1d4a-121">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="b1d4a-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [<span data-ttu-id="b1d4a-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="b1d4a-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
