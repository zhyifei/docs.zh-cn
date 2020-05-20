---
title: IBindingDisplay::GetCurrentDisplay 方法
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: 6fe8c3266a8c9a52cd1022589cd68485c4326fd1
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442184"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="d8c97-102">IBindingDisplay::GetCurrentDisplay 方法</span><span class="sxs-lookup"><span data-stu-id="d8c97-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="d8c97-103">返回当前绑定显示信息。</span><span class="sxs-lookup"><span data-stu-id="d8c97-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8c97-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8c97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8c97-105">参数</span><span class="sxs-lookup"><span data-stu-id="d8c97-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="d8c97-106">[out，retval]指向包含绑定显示信息的 safearray 的指针。</span><span class="sxs-lookup"><span data-stu-id="d8c97-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8c97-107">备注</span><span class="sxs-lookup"><span data-stu-id="d8c97-107">Remarks</span></span>  
 <span data-ttu-id="d8c97-108">[IBindingDisplay：： InitializeForProcess](ibindingdisplay-initializeforprocess-method.md)方法之前必须已成功，并且调试器必须停止该程序。</span><span class="sxs-lookup"><span data-stu-id="d8c97-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="d8c97-109">调用方必须使用 SafeArrayDestroy 释放返回的 `SAFEARRAY` 内存[SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)。</span><span class="sxs-lookup"><span data-stu-id="d8c97-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8c97-110">要求</span><span class="sxs-lookup"><span data-stu-id="d8c97-110">Requirements</span></span>  
 <span data-ttu-id="d8c97-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c97-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8c97-112">**标头：** BindingDisplay</span><span class="sxs-lookup"><span data-stu-id="d8c97-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="d8c97-113">**库：** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="d8c97-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="d8c97-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8c97-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c97-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8c97-115">See also</span></span>

- [<span data-ttu-id="d8c97-116">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="d8c97-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="d8c97-117">InitializeForProcess 方法</span><span class="sxs-lookup"><span data-stu-id="d8c97-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
