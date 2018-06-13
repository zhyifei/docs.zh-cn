---
title: ICorConfiguration::AddDebuggerSpecialThread 方法
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59b940c0dbe9462dda513e933b7360ff55a9b447
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437344"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="11265-102">ICorConfiguration::AddDebuggerSpecialThread 方法</span><span class="sxs-lookup"><span data-stu-id="11265-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="11265-103">指示应允许特定线程继续执行而调试器具有应用程序在托管或非托管调试方案期间停止调试服务。</span><span class="sxs-lookup"><span data-stu-id="11265-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11265-104">语法</span><span class="sxs-lookup"><span data-stu-id="11265-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11265-105">参数</span><span class="sxs-lookup"><span data-stu-id="11265-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="11265-106">[in]应允许继续执行线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="11265-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11265-107">备注</span><span class="sxs-lookup"><span data-stu-id="11265-107">Remarks</span></span>  
 <span data-ttu-id="11265-108">将不允许指定的线程运行托管的代码或以任何方式进入运行时。</span><span class="sxs-lookup"><span data-stu-id="11265-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="11265-109">此类线程的示例将以支持旧版脚本调试器中进程线程。</span><span class="sxs-lookup"><span data-stu-id="11265-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11265-110">要求</span><span class="sxs-lookup"><span data-stu-id="11265-110">Requirements</span></span>  
 <span data-ttu-id="11265-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11265-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11265-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11265-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11265-113">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="11265-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11265-114">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11265-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11265-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="11265-115">See Also</span></span>  
 [<span data-ttu-id="11265-116">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="11265-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
