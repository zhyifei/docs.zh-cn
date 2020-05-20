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
ms.openlocfilehash: 8645878132359b6218cd62b1ff707208de53704b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442145"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="6af50-102">IBindingDisplay::InitializeForProcess 方法</span><span class="sxs-lookup"><span data-stu-id="6af50-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="6af50-103">初始化[IBindingDisplay](ibindingdisplay-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="6af50-103">Initializes the [IBindingDisplay](ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af50-104">语法</span><span class="sxs-lookup"><span data-stu-id="6af50-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6af50-105">参数</span><span class="sxs-lookup"><span data-stu-id="6af50-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="6af50-106">中进程标识符。</span><span class="sxs-lookup"><span data-stu-id="6af50-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6af50-107">备注</span><span class="sxs-lookup"><span data-stu-id="6af50-107">Remarks</span></span>  
 <span data-ttu-id="6af50-108">调试器 `InitializeForProcess` 在创建时调用方法以初始化绑定显示。</span><span class="sxs-lookup"><span data-stu-id="6af50-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="6af50-109">`InitializeForProcess`调用任何其他方法之前，必须在创建时调用 `IBindingDisplay` 。</span><span class="sxs-lookup"><span data-stu-id="6af50-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6af50-110">要求</span><span class="sxs-lookup"><span data-stu-id="6af50-110">Requirements</span></span>  
 <span data-ttu-id="6af50-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6af50-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6af50-112">**标头：** BindingDisplay</span><span class="sxs-lookup"><span data-stu-id="6af50-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="6af50-113">**库：** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="6af50-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="6af50-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6af50-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af50-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6af50-115">See also</span></span>

- [<span data-ttu-id="6af50-116">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="6af50-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
