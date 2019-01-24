---
title: ICLRDebuggingLibraryProvider 接口
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9d851a31cbbf429f49b9f369ce9bc03fa110b5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731980"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="983f5-102">ICLRDebuggingLibraryProvider 接口</span><span class="sxs-lookup"><span data-stu-id="983f5-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="983f5-103">包括[ProvideLibrary 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)方法，获取一个库提供程序允许公共语言运行时特定于版本的调试库定位和加载根据需要的回调接口。</span><span class="sxs-lookup"><span data-stu-id="983f5-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="983f5-104">方法</span><span class="sxs-lookup"><span data-stu-id="983f5-104">Methods</span></span>  
  
|<span data-ttu-id="983f5-105">方法</span><span class="sxs-lookup"><span data-stu-id="983f5-105">Method</span></span>|<span data-ttu-id="983f5-106">描述</span><span class="sxs-lookup"><span data-stu-id="983f5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="983f5-107">ProvideLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="983f5-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="983f5-108">使调试器能够提供可用于加载调试库中的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="983f5-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="983f5-109">要求</span><span class="sxs-lookup"><span data-stu-id="983f5-109">Requirements</span></span>  
 <span data-ttu-id="983f5-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="983f5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983f5-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="983f5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="983f5-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="983f5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="983f5-113">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983f5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="983f5-114">See also</span></span>
- [<span data-ttu-id="983f5-115">调试接口</span><span class="sxs-lookup"><span data-stu-id="983f5-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="983f5-116">调试</span><span class="sxs-lookup"><span data-stu-id="983f5-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
