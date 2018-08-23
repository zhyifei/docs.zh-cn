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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 889456f08c967c807b4d3d09508af000035ebdaf
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "42755075"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="222cf-102">IBindingDisplay::GetCurrentDisplay 方法</span><span class="sxs-lookup"><span data-stu-id="222cf-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="222cf-103">返回当前绑定显示信息。</span><span class="sxs-lookup"><span data-stu-id="222cf-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="222cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="222cf-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="222cf-105">参数</span><span class="sxs-lookup"><span data-stu-id="222cf-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="222cf-106">[out，retval]指向包含绑定显示信息的 safearray 的指针。</span><span class="sxs-lookup"><span data-stu-id="222cf-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="222cf-107">备注</span><span class="sxs-lookup"><span data-stu-id="222cf-107">Remarks</span></span>  
 <span data-ttu-id="222cf-108">[Ibindingdisplay:: Initializeforprocess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)方法必须具有先前已成功，并且必须由调试器停止程序。</span><span class="sxs-lookup"><span data-stu-id="222cf-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="222cf-109">调用方必须释放返回`SAFEARRAY`使用的内存[SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)。</span><span class="sxs-lookup"><span data-stu-id="222cf-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="222cf-110">要求</span><span class="sxs-lookup"><span data-stu-id="222cf-110">Requirements</span></span>  
 <span data-ttu-id="222cf-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="222cf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="222cf-112">**标头：** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="222cf-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="222cf-113">**库：** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="222cf-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="222cf-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="222cf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="222cf-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="222cf-115">See Also</span></span>  
 [<span data-ttu-id="222cf-116">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="222cf-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 [<span data-ttu-id="222cf-117">InitializeForProcess 方法</span><span class="sxs-lookup"><span data-stu-id="222cf-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
