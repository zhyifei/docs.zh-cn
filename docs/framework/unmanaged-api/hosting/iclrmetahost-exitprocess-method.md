---
title: "ICLRMetaHost::ExitProcess 方法"
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
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2407dd8fb4911bd7e6d46c973ebbab836da4f8fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="f5636-102">ICLRMetaHost::ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="f5636-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="f5636-103">尝试正常关闭所有已加载的运行时，然后终止该进程。</span><span class="sxs-lookup"><span data-stu-id="f5636-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="f5636-104">取代[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="f5636-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5636-105">语法</span><span class="sxs-lookup"><span data-stu-id="f5636-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5636-106">参数</span><span class="sxs-lookup"><span data-stu-id="f5636-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="f5636-107">[in]进程的退出代码。</span><span class="sxs-lookup"><span data-stu-id="f5636-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5636-108">返回值</span><span class="sxs-lookup"><span data-stu-id="f5636-108">Return Value</span></span>  
 <span data-ttu-id="f5636-109">永远不会返回此方法，以便其返回值是不确定。</span><span class="sxs-lookup"><span data-stu-id="f5636-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5636-110">备注</span><span class="sxs-lookup"><span data-stu-id="f5636-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5636-111">惠?</span><span class="sxs-lookup"><span data-stu-id="f5636-111">Requirements</span></span>  
 <span data-ttu-id="f5636-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5636-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5636-113">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f5636-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f5636-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f5636-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5636-115">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5636-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5636-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5636-116">See Also</span></span>  
 [<span data-ttu-id="f5636-117">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="f5636-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="f5636-118">承载</span><span class="sxs-lookup"><span data-stu-id="f5636-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
