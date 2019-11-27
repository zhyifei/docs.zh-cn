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
ms.openlocfilehash: 9294dbf1caddd4b607185de54efd2b4764e6ca35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448502"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="97ec9-102">IBindingDisplay::GetCurrentDisplay 方法</span><span class="sxs-lookup"><span data-stu-id="97ec9-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="97ec9-103">返回当前绑定显示信息。</span><span class="sxs-lookup"><span data-stu-id="97ec9-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ec9-104">语法</span><span class="sxs-lookup"><span data-stu-id="97ec9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97ec9-105">参数</span><span class="sxs-lookup"><span data-stu-id="97ec9-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="97ec9-106">[out，retval]指向包含绑定显示信息的 safearray 的指针。</span><span class="sxs-lookup"><span data-stu-id="97ec9-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97ec9-107">备注</span><span class="sxs-lookup"><span data-stu-id="97ec9-107">Remarks</span></span>  
 <span data-ttu-id="97ec9-108">[IBindingDisplay：： InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)方法之前必须已成功，并且调试器必须停止该程序。</span><span class="sxs-lookup"><span data-stu-id="97ec9-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="97ec9-109">调用方必须使用[SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)释放返回的 `SAFEARRAY` 内存。</span><span class="sxs-lookup"><span data-stu-id="97ec9-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97ec9-110">要求</span><span class="sxs-lookup"><span data-stu-id="97ec9-110">Requirements</span></span>  
 <span data-ttu-id="97ec9-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97ec9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97ec9-112">**标头：** BindingDisplay</span><span class="sxs-lookup"><span data-stu-id="97ec9-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="97ec9-113">**库：** BindingDisplay .idl</span><span class="sxs-lookup"><span data-stu-id="97ec9-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="97ec9-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97ec9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ec9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97ec9-115">See also</span></span>

- [<span data-ttu-id="97ec9-116">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="97ec9-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="97ec9-117">InitializeForProcess 方法</span><span class="sxs-lookup"><span data-stu-id="97ec9-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
