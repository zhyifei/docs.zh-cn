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
ms.openlocfilehash: fc71762fb4a660cf84814cdd46d09696a161f3c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431592"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="44389-102">ICLRMetaHost::ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="44389-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="44389-103">尝试正常关闭所有已加载的运行时，然后终止该进程。</span><span class="sxs-lookup"><span data-stu-id="44389-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="44389-104">取代[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="44389-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44389-105">语法</span><span class="sxs-lookup"><span data-stu-id="44389-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44389-106">参数</span><span class="sxs-lookup"><span data-stu-id="44389-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="44389-107">[in]进程的退出代码。</span><span class="sxs-lookup"><span data-stu-id="44389-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44389-108">返回值</span><span class="sxs-lookup"><span data-stu-id="44389-108">Return Value</span></span>  
 <span data-ttu-id="44389-109">永远不会返回此方法，以便其返回值是不确定。</span><span class="sxs-lookup"><span data-stu-id="44389-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44389-110">备注</span><span class="sxs-lookup"><span data-stu-id="44389-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44389-111">要求</span><span class="sxs-lookup"><span data-stu-id="44389-111">Requirements</span></span>  
 <span data-ttu-id="44389-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44389-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44389-113">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="44389-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="44389-114">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="44389-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44389-115">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44389-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44389-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="44389-116">See Also</span></span>  
 [<span data-ttu-id="44389-117">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="44389-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="44389-118">承载</span><span class="sxs-lookup"><span data-stu-id="44389-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
