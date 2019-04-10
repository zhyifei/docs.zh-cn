---
title: ICLRMetaHost::ExitProcess 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64c212d064ad658678926690d1e680afe27c7c99
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219234"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="7d8c9-102">ICLRMetaHost::ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="7d8c9-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="7d8c9-103">尝试正常关闭所有已加载运行时，然后终止该进程。</span><span class="sxs-lookup"><span data-stu-id="7d8c9-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="7d8c9-104">取代[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="7d8c9-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d8c9-105">语法</span><span class="sxs-lookup"><span data-stu-id="7d8c9-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d8c9-106">参数</span><span class="sxs-lookup"><span data-stu-id="7d8c9-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="7d8c9-107">[in]进程退出代码。</span><span class="sxs-lookup"><span data-stu-id="7d8c9-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d8c9-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7d8c9-108">Return Value</span></span>  
 <span data-ttu-id="7d8c9-109">永远不会返回此方法，因此其返回值是未定义。</span><span class="sxs-lookup"><span data-stu-id="7d8c9-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d8c9-110">备注</span><span class="sxs-lookup"><span data-stu-id="7d8c9-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d8c9-111">要求</span><span class="sxs-lookup"><span data-stu-id="7d8c9-111">Requirements</span></span>  
 <span data-ttu-id="7d8c9-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d8c9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d8c9-113">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7d8c9-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7d8c9-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7d8c9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7d8c9-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="7d8c9-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7d8c9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d8c9-116">See also</span></span>

- [<span data-ttu-id="7d8c9-117">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="7d8c9-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="7d8c9-118">宿主</span><span class="sxs-lookup"><span data-stu-id="7d8c9-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
