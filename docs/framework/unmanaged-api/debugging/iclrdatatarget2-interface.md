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
ms.openlocfilehash: bdc8378a129dd5bb1d9fdcb080c7b5cd53d34091
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789076"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="429b5-102">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="429b5-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="429b5-103">数据访问服务层用于处理目标进程中的虚拟内存区域的[ICLRDataTarget](iclrdatatarget-interface.md)的子类。</span><span class="sxs-lookup"><span data-stu-id="429b5-103">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="429b5-104">方法</span><span class="sxs-lookup"><span data-stu-id="429b5-104">Methods</span></span>  
  
|<span data-ttu-id="429b5-105">方法</span><span class="sxs-lookup"><span data-stu-id="429b5-105">Method</span></span>|<span data-ttu-id="429b5-106">描述</span><span class="sxs-lookup"><span data-stu-id="429b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="429b5-107">AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="429b5-107">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="429b5-108">在目标进程的地址空间中分配内存。</span><span class="sxs-lookup"><span data-stu-id="429b5-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="429b5-109">FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="429b5-109">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="429b5-110">释放以前在目标进程的地址空间中分配的内存。</span><span class="sxs-lookup"><span data-stu-id="429b5-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="429b5-111">备注</span><span class="sxs-lookup"><span data-stu-id="429b5-111">Remarks</span></span>  
 <span data-ttu-id="429b5-112">API 客户端（即调试器）必须针对特定的目标进程实现此接口。</span><span class="sxs-lookup"><span data-stu-id="429b5-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="429b5-113">例如，活动进程的实现将不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="429b5-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="429b5-114">目标可能不支持对其内存区域的修改。</span><span class="sxs-lookup"><span data-stu-id="429b5-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="429b5-115">需求</span><span class="sxs-lookup"><span data-stu-id="429b5-115">Requirements</span></span>  
 <span data-ttu-id="429b5-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="429b5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="429b5-117">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="429b5-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="429b5-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="429b5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="429b5-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="429b5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="429b5-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="429b5-120">See also</span></span>

- [<span data-ttu-id="429b5-121">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="429b5-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="429b5-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="429b5-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
