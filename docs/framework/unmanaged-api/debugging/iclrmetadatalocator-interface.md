---
title: "ICLRMetadataLocator 接口"
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
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a06997c47a85ced56dc579759192f7256def4f5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="ace0e-102">ICLRMetadataLocator 接口</span><span class="sxs-lookup"><span data-stu-id="ace0e-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="ace0e-103">由数据访问服务层用于在目标进程中查找程序集的元数据。</span><span class="sxs-lookup"><span data-stu-id="ace0e-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ace0e-104">方法</span><span class="sxs-lookup"><span data-stu-id="ace0e-104">Methods</span></span>  
  
|<span data-ttu-id="ace0e-105">方法</span><span class="sxs-lookup"><span data-stu-id="ace0e-105">Method</span></span>|<span data-ttu-id="ace0e-106">描述</span><span class="sxs-lookup"><span data-stu-id="ace0e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ace0e-107">GetMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="ace0e-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="ace0e-108">从目标进程中检索映像的元数据。</span><span class="sxs-lookup"><span data-stu-id="ace0e-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ace0e-109">备注</span><span class="sxs-lookup"><span data-stu-id="ace0e-109">Remarks</span></span>  
 <span data-ttu-id="ace0e-110">API 客户端（即调试器）必须针对特定的目标进程实现此接口。</span><span class="sxs-lookup"><span data-stu-id="ace0e-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="ace0e-111">例如，活动进程的实现是不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="ace0e-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ace0e-112">惠?</span><span class="sxs-lookup"><span data-stu-id="ace0e-112">Requirements</span></span>  
 <span data-ttu-id="ace0e-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ace0e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ace0e-114">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="ace0e-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ace0e-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ace0e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ace0e-116">**.**</span><span class="sxs-lookup"><span data-stu-id="ace0e-116">**.**</span></span> <span data-ttu-id="ace0e-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ace0e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace0e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ace0e-118">See Also</span></span>  
 [<span data-ttu-id="ace0e-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="ace0e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
