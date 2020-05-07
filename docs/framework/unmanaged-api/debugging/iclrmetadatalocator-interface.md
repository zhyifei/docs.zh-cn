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
ms.openlocfilehash: 734f8eaa7c520bbf1ad1208ece42751e967a208a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859728"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="25d22-102">ICLRMetadataLocator 接口</span><span class="sxs-lookup"><span data-stu-id="25d22-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="25d22-103">由数据访问服务层用于在目标进程中查找程序集的元数据。</span><span class="sxs-lookup"><span data-stu-id="25d22-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25d22-104">方法</span><span class="sxs-lookup"><span data-stu-id="25d22-104">Methods</span></span>  
  
|<span data-ttu-id="25d22-105">方法</span><span class="sxs-lookup"><span data-stu-id="25d22-105">Method</span></span>|<span data-ttu-id="25d22-106">说明</span><span class="sxs-lookup"><span data-stu-id="25d22-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25d22-107">GetMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="25d22-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="25d22-108">从目标进程中检索图像的元数据。</span><span class="sxs-lookup"><span data-stu-id="25d22-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25d22-109">备注</span><span class="sxs-lookup"><span data-stu-id="25d22-109">Remarks</span></span>  
 <span data-ttu-id="25d22-110">API 客户端（即调试器）必须针对特定的目标进程实现此接口。</span><span class="sxs-lookup"><span data-stu-id="25d22-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="25d22-111">例如，实时过程的实现与内存转储的实现不同。</span><span class="sxs-lookup"><span data-stu-id="25d22-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25d22-112">要求</span><span class="sxs-lookup"><span data-stu-id="25d22-112">Requirements</span></span>  
 <span data-ttu-id="25d22-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25d22-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25d22-114">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="25d22-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="25d22-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25d22-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25d22-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25d22-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d22-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25d22-117">See also</span></span>

- [<span data-ttu-id="25d22-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="25d22-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
