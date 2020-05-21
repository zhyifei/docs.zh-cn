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
ms.openlocfilehash: 8b6593ad995872f0e0014b1e8bcd8a4b576bbeaf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762418"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="c02e8-102">ICorConfiguration::AddDebuggerSpecialThread 方法</span><span class="sxs-lookup"><span data-stu-id="c02e8-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="c02e8-103">向调试服务指示当调试器在托管或非托管调试方案中停止应用程序时，应允许特定线程继续执行。</span><span class="sxs-lookup"><span data-stu-id="c02e8-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c02e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="c02e8-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c02e8-105">参数</span><span class="sxs-lookup"><span data-stu-id="c02e8-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="c02e8-106">中应该允许继续执行的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="c02e8-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c02e8-107">注解</span><span class="sxs-lookup"><span data-stu-id="c02e8-107">Remarks</span></span>  
 <span data-ttu-id="c02e8-108">不允许指定的线程运行托管代码或以任何方式进入运行时。</span><span class="sxs-lookup"><span data-stu-id="c02e8-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="c02e8-109">此类线程的一个示例就是支持旧版脚本调试器的进程内线程。</span><span class="sxs-lookup"><span data-stu-id="c02e8-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c02e8-110">要求</span><span class="sxs-lookup"><span data-stu-id="c02e8-110">Requirements</span></span>  
 <span data-ttu-id="c02e8-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c02e8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c02e8-112">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c02e8-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c02e8-113">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c02e8-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c02e8-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c02e8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c02e8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c02e8-115">See also</span></span>

- [<span data-ttu-id="c02e8-116">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="c02e8-116">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
