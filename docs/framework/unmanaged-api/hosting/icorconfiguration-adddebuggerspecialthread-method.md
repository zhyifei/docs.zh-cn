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
ms.openlocfilehash: a73232fb9327880f0038097d71698ddf8bf005e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779908"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="9c646-102">ICorConfiguration::AddDebuggerSpecialThread 方法</span><span class="sxs-lookup"><span data-stu-id="9c646-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="9c646-103">指示调试服务应允许在特定线程时调试器已在托管或非托管调试方案过程中停止的应用程序继续执行。</span><span class="sxs-lookup"><span data-stu-id="9c646-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c646-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c646-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c646-105">参数</span><span class="sxs-lookup"><span data-stu-id="9c646-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="9c646-106">[in]应允许继续执行线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="9c646-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c646-107">备注</span><span class="sxs-lookup"><span data-stu-id="9c646-107">Remarks</span></span>  
 <span data-ttu-id="9c646-108">指定的线程不会允许运行托管的代码或以任何方式进入运行时。</span><span class="sxs-lookup"><span data-stu-id="9c646-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="9c646-109">此类线程的示例将一个进程内线程以支持旧脚本调试器。</span><span class="sxs-lookup"><span data-stu-id="9c646-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c646-110">要求</span><span class="sxs-lookup"><span data-stu-id="9c646-110">Requirements</span></span>  
 <span data-ttu-id="9c646-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c646-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c646-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9c646-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c646-113">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9c646-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c646-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c646-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c646-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c646-115">See also</span></span>

- [<span data-ttu-id="9c646-116">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="9c646-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
