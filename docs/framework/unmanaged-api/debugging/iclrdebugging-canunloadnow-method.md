---
title: ICLRDebugging::CanUnloadNow 方法
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
ms.openlocfilehash: 4eb6682ac5a8b7788d97f752f249d85886fba0b6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111654"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="4f327-102">ICLRDebugging::CanUnloadNow 方法</span><span class="sxs-lookup"><span data-stu-id="4f327-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="4f327-103">确定[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)接口提供的库是否仍在使用中或是否可以卸载。</span><span class="sxs-lookup"><span data-stu-id="4f327-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f327-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f327-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f327-105">参数</span><span class="sxs-lookup"><span data-stu-id="4f327-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="4f327-106">中目标进程中的模块的基址。</span><span class="sxs-lookup"><span data-stu-id="4f327-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f327-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4f327-107">Return Value</span></span>  
 <span data-ttu-id="4f327-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="4f327-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4f327-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f327-109">HRESULT</span></span>|<span data-ttu-id="4f327-110">描述</span><span class="sxs-lookup"><span data-stu-id="4f327-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f327-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f327-111">S_OK</span></span>|<span data-ttu-id="4f327-112">可以卸载 `hmodule` 引用的模块。</span><span class="sxs-lookup"><span data-stu-id="4f327-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="4f327-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4f327-113">S_FALSE</span></span>|<span data-ttu-id="4f327-114">`hmodule` 引用的模块仍在使用中。</span><span class="sxs-lookup"><span data-stu-id="4f327-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="4f327-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="4f327-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="4f327-116">指示的模块不是 CLR 模块。</span><span class="sxs-lookup"><span data-stu-id="4f327-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4f327-117">异常</span><span class="sxs-lookup"><span data-stu-id="4f327-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f327-118">备注</span><span class="sxs-lookup"><span data-stu-id="4f327-118">Remarks</span></span>  
 <span data-ttu-id="4f327-119">此方法检查是否已释放 `ICorDebug*` 接口的所有实例，并且当前在对[ICLRDebugging：： OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法的调用中没有线程。</span><span class="sxs-lookup"><span data-stu-id="4f327-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f327-120">要求</span><span class="sxs-lookup"><span data-stu-id="4f327-120">Requirements</span></span>  
 <span data-ttu-id="4f327-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f327-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f327-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f327-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f327-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f327-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f327-124">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f327-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f327-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f327-125">See also</span></span>

- [<span data-ttu-id="4f327-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="4f327-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4f327-127">调试</span><span class="sxs-lookup"><span data-stu-id="4f327-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
