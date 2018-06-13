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
ms.openlocfilehash: 12b7fa5e61ba6f967544d8ebeee2f1c6a8d3a7b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405988"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="25c57-102">ICLRDebugging 接口</span><span class="sxs-lookup"><span data-stu-id="25c57-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="25c57-103">提供一些方法，用于处理模块的加载和卸载以进行调试。</span><span class="sxs-lookup"><span data-stu-id="25c57-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25c57-104">方法</span><span class="sxs-lookup"><span data-stu-id="25c57-104">Methods</span></span>  
  
|<span data-ttu-id="25c57-105">方法</span><span class="sxs-lookup"><span data-stu-id="25c57-105">Method</span></span>|<span data-ttu-id="25c57-106">描述</span><span class="sxs-lookup"><span data-stu-id="25c57-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25c57-107">OpenVirtualProcess 方法</span><span class="sxs-lookup"><span data-stu-id="25c57-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="25c57-108">获取对应于进程中加载了公共语言运行时 (CLR) 模块的"ICorDebugProcess"接口。</span><span class="sxs-lookup"><span data-stu-id="25c57-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="25c57-109">CanUnloadNow 方法</span><span class="sxs-lookup"><span data-stu-id="25c57-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="25c57-110">确定是否由库[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)接口仍在使用或可以卸载。</span><span class="sxs-lookup"><span data-stu-id="25c57-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25c57-111">备注</span><span class="sxs-lookup"><span data-stu-id="25c57-111">Remarks</span></span>  
 <span data-ttu-id="25c57-112">你可以获取的实例`ICLRDebugging`接口使用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="25c57-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25c57-113">要求</span><span class="sxs-lookup"><span data-stu-id="25c57-113">Requirements</span></span>  
 <span data-ttu-id="25c57-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25c57-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25c57-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25c57-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25c57-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25c57-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25c57-117">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25c57-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25c57-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="25c57-118">See Also</span></span>  
 [<span data-ttu-id="25c57-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="25c57-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="25c57-120">调试</span><span class="sxs-lookup"><span data-stu-id="25c57-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
