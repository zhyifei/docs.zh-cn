---
title: CorExitProcess 函数
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b95625cfe17b36c0244e6780a08dcf50ce50763d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201853"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="10ca8-102">CorExitProcess 函数</span><span class="sxs-lookup"><span data-stu-id="10ca8-102">CorExitProcess Function</span></span>
<span data-ttu-id="10ca8-103">关闭当前的非托管进程。</span><span class="sxs-lookup"><span data-stu-id="10ca8-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="10ca8-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="10ca8-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="10ca8-105">使用[iclrmetahost:: Exitprocess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="10ca8-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ca8-106">语法</span><span class="sxs-lookup"><span data-stu-id="10ca8-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10ca8-107">参数</span><span class="sxs-lookup"><span data-stu-id="10ca8-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="10ca8-108">一个整数，指定在进程退出代码。</span><span class="sxs-lookup"><span data-stu-id="10ca8-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10ca8-109">备注</span><span class="sxs-lookup"><span data-stu-id="10ca8-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10ca8-110">开头[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]，`CorExitProcess`退出进程，而不仅仅是传统的 Api 已绑定到的运行时中每个已启动运行时。</span><span class="sxs-lookup"><span data-stu-id="10ca8-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10ca8-111">要求</span><span class="sxs-lookup"><span data-stu-id="10ca8-111">Requirements</span></span>  
 <span data-ttu-id="10ca8-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10ca8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ca8-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10ca8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10ca8-114">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10ca8-114">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="10ca8-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="10ca8-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="10ca8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="10ca8-116">See also</span></span>

- [<span data-ttu-id="10ca8-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="10ca8-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
