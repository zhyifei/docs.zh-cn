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
ms.openlocfilehash: f8e585942cf6b7e368351fde3181402990201d6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="57a15-102">IBindingDisplay::GetCurrentDisplay 方法</span><span class="sxs-lookup"><span data-stu-id="57a15-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="57a15-103">返回当前绑定的显示信息。</span><span class="sxs-lookup"><span data-stu-id="57a15-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57a15-104">语法</span><span class="sxs-lookup"><span data-stu-id="57a15-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57a15-105">参数</span><span class="sxs-lookup"><span data-stu-id="57a15-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="57a15-106">[out，retval]指向 safearray 包含绑定显示信息的指针。</span><span class="sxs-lookup"><span data-stu-id="57a15-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57a15-107">备注</span><span class="sxs-lookup"><span data-stu-id="57a15-107">Remarks</span></span>  
 <span data-ttu-id="57a15-108">[Ibindingdisplay:: Initializeforprocess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)方法必须具有以前成功，并且必须由调试器停止程序。</span><span class="sxs-lookup"><span data-stu-id="57a15-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="57a15-109">调用方必须释放返回`SAFEARRAY`使用的内存[SafeArrayDestroy](http://msdn.microsoft.com/library/fc94f7e7-b903-4c78-905c-54df1f8d13fa)。</span><span class="sxs-lookup"><span data-stu-id="57a15-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](http://msdn.microsoft.com/library/fc94f7e7-b903-4c78-905c-54df1f8d13fa).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57a15-110">要求</span><span class="sxs-lookup"><span data-stu-id="57a15-110">Requirements</span></span>  
 <span data-ttu-id="57a15-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="57a15-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57a15-112">**标头：** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="57a15-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="57a15-113">**库：** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="57a15-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="57a15-114">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57a15-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a15-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="57a15-115">See Also</span></span>  
 [<span data-ttu-id="57a15-116">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="57a15-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 [<span data-ttu-id="57a15-117">InitializeForProcess 方法</span><span class="sxs-lookup"><span data-stu-id="57a15-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
