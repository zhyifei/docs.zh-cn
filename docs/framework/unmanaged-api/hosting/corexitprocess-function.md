---
title: "CorExitProcess 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CorExitProcess
helpviewer_keywords: CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75b35631bad5de46d48ed818c6f929f25a5f7e66
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corexitprocess-function"></a><span data-ttu-id="8b112-102">CorExitProcess 函数</span><span class="sxs-lookup"><span data-stu-id="8b112-102">CorExitProcess Function</span></span>
<span data-ttu-id="8b112-103">关闭当前的非托管进程。</span><span class="sxs-lookup"><span data-stu-id="8b112-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="8b112-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8b112-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="8b112-105">使用[iclrmetahost:: Exitprocess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="8b112-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b112-106">语法</span><span class="sxs-lookup"><span data-stu-id="8b112-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b112-107">参数</span><span class="sxs-lookup"><span data-stu-id="8b112-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="8b112-108">一个整数，指定进程退出代码。</span><span class="sxs-lookup"><span data-stu-id="8b112-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b112-109">备注</span><span class="sxs-lookup"><span data-stu-id="8b112-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b112-110">开头[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]，`CorExitProcess`退出在过程中，而不仅仅是运行时的旧 Api 具有绑定到每个已启动运行时。</span><span class="sxs-lookup"><span data-stu-id="8b112-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b112-111">要求</span><span class="sxs-lookup"><span data-stu-id="8b112-111">Requirements</span></span>  
 <span data-ttu-id="8b112-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b112-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b112-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b112-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b112-114">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b112-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b112-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b112-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b112-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b112-116">See Also</span></span>  
 [<span data-ttu-id="8b112-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="8b112-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
