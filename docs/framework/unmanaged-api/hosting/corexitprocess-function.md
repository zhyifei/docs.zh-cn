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
ms.openlocfilehash: 44578595b3cb790570c5359e714bd39c109cf1f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176456"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="e49ce-102">CorExitProcess 函数</span><span class="sxs-lookup"><span data-stu-id="e49ce-102">CorExitProcess Function</span></span>
<span data-ttu-id="e49ce-103">关闭当前非托管进程。</span><span class="sxs-lookup"><span data-stu-id="e49ce-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="e49ce-104">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="e49ce-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="e49ce-105">改用[ICLRMetaHost：：退出进程](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e49ce-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e49ce-106">语法</span><span class="sxs-lookup"><span data-stu-id="e49ce-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e49ce-107">parameters</span><span class="sxs-lookup"><span data-stu-id="e49ce-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="e49ce-108">指定进程退出代码的整数。</span><span class="sxs-lookup"><span data-stu-id="e49ce-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e49ce-109">备注</span><span class="sxs-lookup"><span data-stu-id="e49ce-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e49ce-110">从 .NET 框架 4`CorExitProcess`开始，退出进程中的每个启动运行时，而不仅仅是将旧 API 绑定到的运行时。</span><span class="sxs-lookup"><span data-stu-id="e49ce-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e49ce-111">要求</span><span class="sxs-lookup"><span data-stu-id="e49ce-111">Requirements</span></span>  
 <span data-ttu-id="e49ce-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e49ce-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e49ce-113">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e49ce-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e49ce-114">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e49ce-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e49ce-115">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e49ce-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e49ce-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e49ce-116">See also</span></span>

- [<span data-ttu-id="e49ce-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="e49ce-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
