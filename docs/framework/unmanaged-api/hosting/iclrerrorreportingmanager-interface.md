---
title: ICLRErrorReportingManager 接口
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a20b79dd5eda9c431511cc49e7e3adaa9486b2aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155982"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="3d907-102">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="3d907-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="3d907-103">提供允许主机配置为错误报告的自定义的堆栈转储的方法。</span><span class="sxs-lookup"><span data-stu-id="3d907-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d907-104">方法</span><span class="sxs-lookup"><span data-stu-id="3d907-104">Methods</span></span>  
  
|<span data-ttu-id="3d907-105">方法</span><span class="sxs-lookup"><span data-stu-id="3d907-105">Method</span></span>|<span data-ttu-id="3d907-106">描述</span><span class="sxs-lookup"><span data-stu-id="3d907-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d907-107">BeginCustomDump 方法</span><span class="sxs-lookup"><span data-stu-id="3d907-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="3d907-108">指定的错误报告的自定义的堆栈转储的配置。</span><span class="sxs-lookup"><span data-stu-id="3d907-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="3d907-109">EndCustomDump 方法</span><span class="sxs-lookup"><span data-stu-id="3d907-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="3d907-110">清除以前通过调用所设置的自定义的堆栈转储配置`BeginCustomDump`。</span><span class="sxs-lookup"><span data-stu-id="3d907-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="3d907-111">GetBucketParametersForCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="3d907-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="3d907-112">获取调用线程上的当前异常的 Watson 存储桶。</span><span class="sxs-lookup"><span data-stu-id="3d907-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d907-113">备注</span><span class="sxs-lookup"><span data-stu-id="3d907-113">Remarks</span></span>  
 <span data-ttu-id="3d907-114">`BeginCustomDump`方法设置自定义的堆栈转储配置。</span><span class="sxs-lookup"><span data-stu-id="3d907-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="3d907-115">`EndCustomDump`方法清除自定义的堆栈转储配置，并释放任何关联的状态。</span><span class="sxs-lookup"><span data-stu-id="3d907-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="3d907-116">自定义的转储完成后，应调用它。</span><span class="sxs-lookup"><span data-stu-id="3d907-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3d907-117">调用失败`EndCustomDump`导致内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="3d907-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d907-118">要求</span><span class="sxs-lookup"><span data-stu-id="3d907-118">Requirements</span></span>  
 <span data-ttu-id="3d907-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3d907-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d907-120">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3d907-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d907-121">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3d907-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3d907-122">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3d907-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d907-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d907-123">See also</span></span>

- [<span data-ttu-id="3d907-124">ECustomDumpItemKind 枚举</span><span class="sxs-lookup"><span data-stu-id="3d907-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="3d907-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="3d907-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
