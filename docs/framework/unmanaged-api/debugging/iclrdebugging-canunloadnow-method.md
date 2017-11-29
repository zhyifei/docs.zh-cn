---
title: "ICLRDebugging::CanUnloadNow 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging.CanUnloadNow Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b013231666ca6dfde5ab16e58023da1ae2a72941
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="4ca55-102">ICLRDebugging::CanUnloadNow 方法</span><span class="sxs-lookup"><span data-stu-id="4ca55-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="4ca55-103">确定是否由库[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)接口仍在使用或可以卸载。</span><span class="sxs-lookup"><span data-stu-id="4ca55-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca55-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ca55-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4ca55-105">参数</span><span class="sxs-lookup"><span data-stu-id="4ca55-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="4ca55-106">[in]目标进程中的模块基址。</span><span class="sxs-lookup"><span data-stu-id="4ca55-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ca55-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4ca55-107">Return Value</span></span>  
 <span data-ttu-id="4ca55-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="4ca55-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4ca55-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ca55-109">HRESULT</span></span>|<span data-ttu-id="4ca55-110">描述</span><span class="sxs-lookup"><span data-stu-id="4ca55-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ca55-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ca55-111">S_OK</span></span>|<span data-ttu-id="4ca55-112">被引用的模块`hmodule`可以卸载。</span><span class="sxs-lookup"><span data-stu-id="4ca55-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="4ca55-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4ca55-113">S_FALSE</span></span>|<span data-ttu-id="4ca55-114">被引用的模块`hmodule`仍在使用。</span><span class="sxs-lookup"><span data-stu-id="4ca55-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="4ca55-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="4ca55-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="4ca55-116">所指示的模块不是 CLR 模块。</span><span class="sxs-lookup"><span data-stu-id="4ca55-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4ca55-117">异常</span><span class="sxs-lookup"><span data-stu-id="4ca55-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ca55-118">备注</span><span class="sxs-lookup"><span data-stu-id="4ca55-118">Remarks</span></span>  
 <span data-ttu-id="4ca55-119">此方法将检查以查看所有的实例`ICorDebug*`接口已发布，且无需对线程当前处于调用[iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4ca55-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ca55-120">要求</span><span class="sxs-lookup"><span data-stu-id="4ca55-120">Requirements</span></span>  
 <span data-ttu-id="4ca55-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4ca55-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ca55-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ca55-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ca55-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ca55-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ca55-124">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ca55-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca55-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ca55-125">See Also</span></span>  
 [<span data-ttu-id="4ca55-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="4ca55-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4ca55-127">调试</span><span class="sxs-lookup"><span data-stu-id="4ca55-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
