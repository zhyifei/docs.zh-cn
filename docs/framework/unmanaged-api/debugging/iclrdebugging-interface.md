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
ms.openlocfilehash: a3d4297e3b16dd1637e6293dbf7f04d4fbeda50f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860380"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="6153b-102">ICLRDebugging 接口</span><span class="sxs-lookup"><span data-stu-id="6153b-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="6153b-103">提供一些方法，用于处理模块的加载和卸载以进行调试。</span><span class="sxs-lookup"><span data-stu-id="6153b-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6153b-104">方法</span><span class="sxs-lookup"><span data-stu-id="6153b-104">Methods</span></span>  
  
|<span data-ttu-id="6153b-105">方法</span><span class="sxs-lookup"><span data-stu-id="6153b-105">Method</span></span>|<span data-ttu-id="6153b-106">说明</span><span class="sxs-lookup"><span data-stu-id="6153b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6153b-107">OpenVirtualProcess 方法</span><span class="sxs-lookup"><span data-stu-id="6153b-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="6153b-108">获取与进程中加载的公共语言运行时（CLR）模块相对应的 "ICorDebugProcess" 接口。</span><span class="sxs-lookup"><span data-stu-id="6153b-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="6153b-109">CanUnloadNow 方法</span><span class="sxs-lookup"><span data-stu-id="6153b-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="6153b-110">确定[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)接口提供的库是否仍在使用中或是否可以卸载。</span><span class="sxs-lookup"><span data-stu-id="6153b-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6153b-111">备注</span><span class="sxs-lookup"><span data-stu-id="6153b-111">Remarks</span></span>  
 <span data-ttu-id="6153b-112">可以使用`ICLRDebugging` [CLRCreateInstance](../hosting/clrcreateinstance-function.md)函数获取接口的实例。</span><span class="sxs-lookup"><span data-stu-id="6153b-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6153b-113">要求</span><span class="sxs-lookup"><span data-stu-id="6153b-113">Requirements</span></span>  
 <span data-ttu-id="6153b-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6153b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6153b-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6153b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6153b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6153b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6153b-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6153b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6153b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6153b-118">See also</span></span>

- [<span data-ttu-id="6153b-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="6153b-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6153b-120">调试</span><span class="sxs-lookup"><span data-stu-id="6153b-120">Debugging</span></span>](index.md)
