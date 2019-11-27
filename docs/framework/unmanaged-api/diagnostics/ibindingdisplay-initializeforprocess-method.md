---
title: IBindingDisplay::InitializeForProcess 方法
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
ms.openlocfilehash: bb796a12868cc3e44394ab493f7838dc48ab4dc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448492"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="cd4ba-102">IBindingDisplay::InitializeForProcess 方法</span><span class="sxs-lookup"><span data-stu-id="cd4ba-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="cd4ba-103">初始化[IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="cd4ba-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd4ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd4ba-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd4ba-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd4ba-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="cd4ba-106">中进程标识符。</span><span class="sxs-lookup"><span data-stu-id="cd4ba-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd4ba-107">备注</span><span class="sxs-lookup"><span data-stu-id="cd4ba-107">Remarks</span></span>  
 <span data-ttu-id="cd4ba-108">调试器在创建时调用 `InitializeForProcess` 方法来初始化绑定显示。</span><span class="sxs-lookup"><span data-stu-id="cd4ba-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="cd4ba-109">在调用 `IBindingDisplay` 上的任何其他方法之前，必须在创建时调用 `InitializeForProcess`。</span><span class="sxs-lookup"><span data-stu-id="cd4ba-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd4ba-110">要求</span><span class="sxs-lookup"><span data-stu-id="cd4ba-110">Requirements</span></span>  
 <span data-ttu-id="cd4ba-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd4ba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd4ba-112">**标头：** BindingDisplay</span><span class="sxs-lookup"><span data-stu-id="cd4ba-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="cd4ba-113">**库：** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="cd4ba-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="cd4ba-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd4ba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd4ba-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd4ba-115">See also</span></span>

- [<span data-ttu-id="cd4ba-116">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="cd4ba-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
