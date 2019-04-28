---
title: ICLRDebugging 接口
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6edee34c8560c989040475fee4a35c6bd2ddb3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697987"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="24725-102">ICLRDebugging 接口</span><span class="sxs-lookup"><span data-stu-id="24725-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="24725-103">提供一些方法，用于处理模块的加载和卸载以进行调试。</span><span class="sxs-lookup"><span data-stu-id="24725-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24725-104">方法</span><span class="sxs-lookup"><span data-stu-id="24725-104">Methods</span></span>  
  
|<span data-ttu-id="24725-105">方法</span><span class="sxs-lookup"><span data-stu-id="24725-105">Method</span></span>|<span data-ttu-id="24725-106">描述</span><span class="sxs-lookup"><span data-stu-id="24725-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24725-107">OpenVirtualProcess 方法</span><span class="sxs-lookup"><span data-stu-id="24725-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="24725-108">获取对应于在进程中加载了公共语言运行时 (CLR) 模块的"ICorDebugProcess"接口。</span><span class="sxs-lookup"><span data-stu-id="24725-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="24725-109">CanUnloadNow 方法</span><span class="sxs-lookup"><span data-stu-id="24725-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="24725-110">确定是否通过提供的库[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)接口仍在使用或可被卸载。</span><span class="sxs-lookup"><span data-stu-id="24725-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24725-111">备注</span><span class="sxs-lookup"><span data-stu-id="24725-111">Remarks</span></span>  
 <span data-ttu-id="24725-112">你可以获取的实例`ICLRDebugging`通过使用接口[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="24725-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24725-113">要求</span><span class="sxs-lookup"><span data-stu-id="24725-113">Requirements</span></span>  
 <span data-ttu-id="24725-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24725-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24725-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24725-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24725-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24725-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24725-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24725-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24725-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="24725-118">See also</span></span>

- [<span data-ttu-id="24725-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="24725-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="24725-120">调试</span><span class="sxs-lookup"><span data-stu-id="24725-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
