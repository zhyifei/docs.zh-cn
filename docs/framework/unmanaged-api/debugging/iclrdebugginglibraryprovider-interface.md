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
ms.openlocfilehash: 77c2011ce677d1bd2823d47740782f48151b408a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860278"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="099a1-102">ICLRDebuggingLibraryProvider 接口</span><span class="sxs-lookup"><span data-stu-id="099a1-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="099a1-103">包括[ProvideLibrary 方法](iclrdebugginglibraryprovider-providelibrary-method.md)方法，该方法可获取一个库提供程序回调接口，该接口允许根据需要定位和加载特定于公共语言运行时版本的调试库。</span><span class="sxs-lookup"><span data-stu-id="099a1-103">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="099a1-104">方法</span><span class="sxs-lookup"><span data-stu-id="099a1-104">Methods</span></span>  
  
|<span data-ttu-id="099a1-105">方法</span><span class="sxs-lookup"><span data-stu-id="099a1-105">Method</span></span>|<span data-ttu-id="099a1-106">说明</span><span class="sxs-lookup"><span data-stu-id="099a1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="099a1-107">ProvideLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="099a1-107">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="099a1-108">允许调试器提供可用于加载调试库的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="099a1-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="099a1-109">要求</span><span class="sxs-lookup"><span data-stu-id="099a1-109">Requirements</span></span>  
 <span data-ttu-id="099a1-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="099a1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="099a1-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="099a1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="099a1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="099a1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="099a1-113">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="099a1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="099a1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="099a1-114">See also</span></span>

- [<span data-ttu-id="099a1-115">调试接口</span><span class="sxs-lookup"><span data-stu-id="099a1-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="099a1-116">调试</span><span class="sxs-lookup"><span data-stu-id="099a1-116">Debugging</span></span>](index.md)
