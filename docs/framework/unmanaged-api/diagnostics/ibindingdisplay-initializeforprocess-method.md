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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa1e85751f90c34d40e88207af5c7eed2dd1bb82
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599334"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="f4ccd-102">IBindingDisplay::InitializeForProcess 方法</span><span class="sxs-lookup"><span data-stu-id="f4ccd-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="f4ccd-103">初始化[IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="f4ccd-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4ccd-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4ccd-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4ccd-105">参数</span><span class="sxs-lookup"><span data-stu-id="f4ccd-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="f4ccd-106">[in]进程标识符。</span><span class="sxs-lookup"><span data-stu-id="f4ccd-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4ccd-107">备注</span><span class="sxs-lookup"><span data-stu-id="f4ccd-107">Remarks</span></span>  
 <span data-ttu-id="f4ccd-108">该调试器将调用`InitializeForProcess`在创建时初始化绑定显示的方法。</span><span class="sxs-lookup"><span data-stu-id="f4ccd-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="f4ccd-109">`InitializeForProcess` 必须在任何其他方法之前在创建时调用`IBindingDisplay`调用。</span><span class="sxs-lookup"><span data-stu-id="f4ccd-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4ccd-110">要求</span><span class="sxs-lookup"><span data-stu-id="f4ccd-110">Requirements</span></span>  
 <span data-ttu-id="f4ccd-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4ccd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4ccd-112">**标头：** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="f4ccd-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="f4ccd-113">**库：** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="f4ccd-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="f4ccd-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4ccd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ccd-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4ccd-115">See also</span></span>

- [<span data-ttu-id="f4ccd-116">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="f4ccd-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
