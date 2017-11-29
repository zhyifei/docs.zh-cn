---
title: "ICLRErrorReportingManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager
helpviewer_keywords: ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590cd87d6a566e9c8c3819fd1b250997938e9c35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="3fb02-102">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="3fb02-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="3fb02-103">提供使该主机可配置的错误报告的自定义堆栈转储的方法。</span><span class="sxs-lookup"><span data-stu-id="3fb02-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fb02-104">方法</span><span class="sxs-lookup"><span data-stu-id="3fb02-104">Methods</span></span>  
  
|<span data-ttu-id="3fb02-105">方法</span><span class="sxs-lookup"><span data-stu-id="3fb02-105">Method</span></span>|<span data-ttu-id="3fb02-106">描述</span><span class="sxs-lookup"><span data-stu-id="3fb02-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3fb02-107">BeginCustomDump 方法</span><span class="sxs-lookup"><span data-stu-id="3fb02-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="3fb02-108">指定的错误报告的自定义堆栈转储的配置。</span><span class="sxs-lookup"><span data-stu-id="3fb02-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="3fb02-109">EndCustomDump 方法</span><span class="sxs-lookup"><span data-stu-id="3fb02-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="3fb02-110">清除以前调用所设置的自定义堆栈转储配置`BeginCustomDump`。</span><span class="sxs-lookup"><span data-stu-id="3fb02-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="3fb02-111">GetBucketParametersForCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="3fb02-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="3fb02-112">获取在调用线程上的当前异常的 Watson bucket。</span><span class="sxs-lookup"><span data-stu-id="3fb02-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fb02-113">备注</span><span class="sxs-lookup"><span data-stu-id="3fb02-113">Remarks</span></span>  
 <span data-ttu-id="3fb02-114">`BeginCustomDump`方法设置自定义堆栈转储配置。</span><span class="sxs-lookup"><span data-stu-id="3fb02-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="3fb02-115">`EndCustomDump`方法清除自定义堆栈转储配置并释放任何关联的状态。</span><span class="sxs-lookup"><span data-stu-id="3fb02-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="3fb02-116">自定义转储完成之后才调用它。</span><span class="sxs-lookup"><span data-stu-id="3fb02-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3fb02-117">调用失败`EndCustomDump`导致内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="3fb02-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fb02-118">要求</span><span class="sxs-lookup"><span data-stu-id="3fb02-118">Requirements</span></span>  
 <span data-ttu-id="3fb02-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fb02-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fb02-120">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fb02-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fb02-121">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3fb02-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fb02-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fb02-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb02-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fb02-123">See Also</span></span>  
 [<span data-ttu-id="3fb02-124">ECustomDumpItemKind 枚举</span><span class="sxs-lookup"><span data-stu-id="3fb02-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="3fb02-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="3fb02-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
