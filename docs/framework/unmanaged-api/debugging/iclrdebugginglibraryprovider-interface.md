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
ms.openlocfilehash: a8d9348572ec0cf67c5facebb2053a7091661724
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793600"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="6f43c-102">ICLRDebuggingLibraryProvider 接口</span><span class="sxs-lookup"><span data-stu-id="6f43c-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="6f43c-103">包括[ProvideLibrary 方法](iclrdebugginglibraryprovider-providelibrary-method.md)方法，该方法可获取一个库提供程序回调接口，该接口允许根据需要定位和加载特定于公共语言运行时版本的调试库。</span><span class="sxs-lookup"><span data-stu-id="6f43c-103">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f43c-104">方法</span><span class="sxs-lookup"><span data-stu-id="6f43c-104">Methods</span></span>  
  
|<span data-ttu-id="6f43c-105">方法</span><span class="sxs-lookup"><span data-stu-id="6f43c-105">Method</span></span>|<span data-ttu-id="6f43c-106">描述</span><span class="sxs-lookup"><span data-stu-id="6f43c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f43c-107">ProvideLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="6f43c-107">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="6f43c-108">允许调试器提供可用于加载调试库的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="6f43c-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f43c-109">需求</span><span class="sxs-lookup"><span data-stu-id="6f43c-109">Requirements</span></span>  
 <span data-ttu-id="6f43c-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6f43c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f43c-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f43c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f43c-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f43c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f43c-113">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f43c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f43c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f43c-114">See also</span></span>

- [<span data-ttu-id="6f43c-115">调试接口</span><span class="sxs-lookup"><span data-stu-id="6f43c-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6f43c-116">调试</span><span class="sxs-lookup"><span data-stu-id="6f43c-116">Debugging</span></span>](index.md)
