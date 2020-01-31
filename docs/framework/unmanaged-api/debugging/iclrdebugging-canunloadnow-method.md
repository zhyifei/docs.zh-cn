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
ms.openlocfilehash: 41b2e009f8f017a72147232015ea2357ae922ca1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793650"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="ee825-102">ICLRDebugging::CanUnloadNow 方法</span><span class="sxs-lookup"><span data-stu-id="ee825-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="ee825-103">确定[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)接口提供的库是否仍在使用中或是否可以卸载。</span><span class="sxs-lookup"><span data-stu-id="ee825-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee825-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee825-104">Syntax</span></span>  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee825-105">参数</span><span class="sxs-lookup"><span data-stu-id="ee825-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="ee825-106">中目标进程中的模块的基址。</span><span class="sxs-lookup"><span data-stu-id="ee825-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee825-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ee825-107">Return Value</span></span>  
 <span data-ttu-id="ee825-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ee825-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ee825-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee825-109">HRESULT</span></span>|<span data-ttu-id="ee825-110">描述</span><span class="sxs-lookup"><span data-stu-id="ee825-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee825-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee825-111">S_OK</span></span>|<span data-ttu-id="ee825-112">可以卸载 `hmodule` 引用的模块。</span><span class="sxs-lookup"><span data-stu-id="ee825-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="ee825-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ee825-113">S_FALSE</span></span>|<span data-ttu-id="ee825-114">`hmodule` 引用的模块仍在使用中。</span><span class="sxs-lookup"><span data-stu-id="ee825-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="ee825-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="ee825-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="ee825-116">指示的模块不是 CLR 模块。</span><span class="sxs-lookup"><span data-stu-id="ee825-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ee825-117">异常</span><span class="sxs-lookup"><span data-stu-id="ee825-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee825-118">备注</span><span class="sxs-lookup"><span data-stu-id="ee825-118">Remarks</span></span>  
 <span data-ttu-id="ee825-119">此方法检查是否已释放 `ICorDebug*` 接口的所有实例，并且当前在对[ICLRDebugging：： OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)方法的调用中没有线程。</span><span class="sxs-lookup"><span data-stu-id="ee825-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee825-120">需求</span><span class="sxs-lookup"><span data-stu-id="ee825-120">Requirements</span></span>  
 <span data-ttu-id="ee825-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee825-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee825-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee825-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee825-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee825-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee825-124">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee825-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee825-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee825-125">See also</span></span>

- [<span data-ttu-id="ee825-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="ee825-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ee825-127">调试</span><span class="sxs-lookup"><span data-stu-id="ee825-127">Debugging</span></span>](index.md)
