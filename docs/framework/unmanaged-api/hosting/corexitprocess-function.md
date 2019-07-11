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
ms.openlocfilehash: 7aaa0e83de1b1c3e2ce436de04a36addef16c057
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758513"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="1716e-102">CorExitProcess 函数</span><span class="sxs-lookup"><span data-stu-id="1716e-102">CorExitProcess Function</span></span>
<span data-ttu-id="1716e-103">关闭当前的非托管进程。</span><span class="sxs-lookup"><span data-stu-id="1716e-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="1716e-104">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="1716e-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="1716e-105">使用[iclrmetahost:: Exitprocess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="1716e-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1716e-106">语法</span><span class="sxs-lookup"><span data-stu-id="1716e-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1716e-107">参数</span><span class="sxs-lookup"><span data-stu-id="1716e-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="1716e-108">一个整数，指定在进程退出代码。</span><span class="sxs-lookup"><span data-stu-id="1716e-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1716e-109">备注</span><span class="sxs-lookup"><span data-stu-id="1716e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1716e-110">从.NET Framework 4 中，开始`CorExitProcess`退出进程，而不仅仅是传统的 Api 已绑定到的运行时中每个已启动运行时。</span><span class="sxs-lookup"><span data-stu-id="1716e-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1716e-111">要求</span><span class="sxs-lookup"><span data-stu-id="1716e-111">Requirements</span></span>  
 <span data-ttu-id="1716e-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1716e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1716e-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1716e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1716e-114">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1716e-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1716e-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1716e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1716e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="1716e-116">See also</span></span>

- [<span data-ttu-id="1716e-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="1716e-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
