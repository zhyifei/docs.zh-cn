---
title: "ICLRDebuggingLibraryProvider 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7320bf261f28fed85c44f2550df5ecd06421290
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="905e9-102">ICLRDebuggingLibraryProvider 接口</span><span class="sxs-lookup"><span data-stu-id="905e9-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="905e9-103">包括[ProvideLibrary 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)方法，后者将获取一个库提供程序允许公共语言运行时特定于版本的调试库需要定位和加载上的回调接口。</span><span class="sxs-lookup"><span data-stu-id="905e9-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="905e9-104">方法</span><span class="sxs-lookup"><span data-stu-id="905e9-104">Methods</span></span>  
  
|<span data-ttu-id="905e9-105">方法</span><span class="sxs-lookup"><span data-stu-id="905e9-105">Method</span></span>|<span data-ttu-id="905e9-106">描述</span><span class="sxs-lookup"><span data-stu-id="905e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="905e9-107">ProvideLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="905e9-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="905e9-108">使调试器能够提供一个可以用于加载调试库的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="905e9-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="905e9-109">惠?</span><span class="sxs-lookup"><span data-stu-id="905e9-109">Requirements</span></span>  
 <span data-ttu-id="905e9-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="905e9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="905e9-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="905e9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="905e9-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="905e9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="905e9-113">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="905e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="905e9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="905e9-114">See Also</span></span>  
 [<span data-ttu-id="905e9-115">调试接口</span><span class="sxs-lookup"><span data-stu-id="905e9-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="905e9-116">调试</span><span class="sxs-lookup"><span data-stu-id="905e9-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
