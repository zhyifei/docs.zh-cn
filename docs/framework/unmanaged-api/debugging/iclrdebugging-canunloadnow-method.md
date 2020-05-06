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
ms.openlocfilehash: 16d15101534b88d7da4093dab73b48b5c09a192c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860402"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="3f8c1-102">ICLRDebugging::CanUnloadNow 方法</span><span class="sxs-lookup"><span data-stu-id="3f8c1-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="3f8c1-103">确定[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)接口提供的库是否仍在使用中或是否可以卸载。</span><span class="sxs-lookup"><span data-stu-id="3f8c1-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f8c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f8c1-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f8c1-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f8c1-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="3f8c1-106">中目标进程中的模块的基址。</span><span class="sxs-lookup"><span data-stu-id="3f8c1-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f8c1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3f8c1-107">Return Value</span></span>  
 <span data-ttu-id="3f8c1-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="3f8c1-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3f8c1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f8c1-109">HRESULT</span></span>|<span data-ttu-id="3f8c1-110">说明</span><span class="sxs-lookup"><span data-stu-id="3f8c1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f8c1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f8c1-111">S_OK</span></span>|<span data-ttu-id="3f8c1-112">`hmodule`可卸载引用的模块。</span><span class="sxs-lookup"><span data-stu-id="3f8c1-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="3f8c1-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3f8c1-113">S_FALSE</span></span>|<span data-ttu-id="3f8c1-114">引用`hmodule`的模块仍在使用中。</span><span class="sxs-lookup"><span data-stu-id="3f8c1-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="3f8c1-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="3f8c1-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="3f8c1-116">指示的模块不是 CLR 模块。</span><span class="sxs-lookup"><span data-stu-id="3f8c1-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="3f8c1-117">异常</span><span class="sxs-lookup"><span data-stu-id="3f8c1-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f8c1-118">备注</span><span class="sxs-lookup"><span data-stu-id="3f8c1-118">Remarks</span></span>  
 <span data-ttu-id="3f8c1-119">此方法检查是否已释放接口的`ICorDebug*`所有实例，并且当前在对[ICLRDebugging：： OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)方法的调用中没有线程。</span><span class="sxs-lookup"><span data-stu-id="3f8c1-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f8c1-120">要求</span><span class="sxs-lookup"><span data-stu-id="3f8c1-120">Requirements</span></span>  
 <span data-ttu-id="3f8c1-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f8c1-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f8c1-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f8c1-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f8c1-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f8c1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f8c1-124">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f8c1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f8c1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f8c1-125">See also</span></span>

- [<span data-ttu-id="3f8c1-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="3f8c1-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3f8c1-127">调试</span><span class="sxs-lookup"><span data-stu-id="3f8c1-127">Debugging</span></span>](index.md)
