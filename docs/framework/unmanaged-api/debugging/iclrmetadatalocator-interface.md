---
title: ICLRMetadataLocator 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddc0429a6fa921e8e6ba3c55f3efe5373bea9576
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697844"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="107da-102">ICLRMetadataLocator 接口</span><span class="sxs-lookup"><span data-stu-id="107da-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="107da-103">由数据访问服务层来在目标进程中查找程序集的元数据。</span><span class="sxs-lookup"><span data-stu-id="107da-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="107da-104">方法</span><span class="sxs-lookup"><span data-stu-id="107da-104">Methods</span></span>  
  
|<span data-ttu-id="107da-105">方法</span><span class="sxs-lookup"><span data-stu-id="107da-105">Method</span></span>|<span data-ttu-id="107da-106">描述</span><span class="sxs-lookup"><span data-stu-id="107da-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="107da-107">GetMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="107da-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="107da-108">从目标进程中检索的图像的元数据。</span><span class="sxs-lookup"><span data-stu-id="107da-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="107da-109">备注</span><span class="sxs-lookup"><span data-stu-id="107da-109">Remarks</span></span>  
 <span data-ttu-id="107da-110">API 客户端（即调试器）必须针对特定的目标进程实现此接口。</span><span class="sxs-lookup"><span data-stu-id="107da-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="107da-111">例如，实时进程的实现将不同的内存转储。</span><span class="sxs-lookup"><span data-stu-id="107da-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="107da-112">要求</span><span class="sxs-lookup"><span data-stu-id="107da-112">Requirements</span></span>  
 <span data-ttu-id="107da-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="107da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="107da-114">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="107da-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="107da-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="107da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="107da-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="107da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="107da-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="107da-117">See also</span></span>

- [<span data-ttu-id="107da-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="107da-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
