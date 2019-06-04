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
ms.openlocfilehash: 2a28b33f80299ae6fce34f9de66b6f7f1bc70ef6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490565"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="36a96-102">CorExitProcess 函数</span><span class="sxs-lookup"><span data-stu-id="36a96-102">CorExitProcess Function</span></span>
<span data-ttu-id="36a96-103">关闭当前的非托管进程。</span><span class="sxs-lookup"><span data-stu-id="36a96-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="36a96-104">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="36a96-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="36a96-105">使用[iclrmetahost:: Exitprocess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="36a96-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36a96-106">语法</span><span class="sxs-lookup"><span data-stu-id="36a96-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36a96-107">参数</span><span class="sxs-lookup"><span data-stu-id="36a96-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="36a96-108">一个整数，指定在进程退出代码。</span><span class="sxs-lookup"><span data-stu-id="36a96-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36a96-109">备注</span><span class="sxs-lookup"><span data-stu-id="36a96-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36a96-110">从.NET Framework 4 中，开始`CorExitProcess`退出进程，而不仅仅是传统的 Api 已绑定到的运行时中每个已启动运行时。</span><span class="sxs-lookup"><span data-stu-id="36a96-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36a96-111">要求</span><span class="sxs-lookup"><span data-stu-id="36a96-111">Requirements</span></span>  
 <span data-ttu-id="36a96-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36a96-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36a96-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="36a96-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36a96-114">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36a96-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36a96-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36a96-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a96-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="36a96-116">See also</span></span>

- [<span data-ttu-id="36a96-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="36a96-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
