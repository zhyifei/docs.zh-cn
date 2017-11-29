---
title: "IBindingDisplay::GetCurrentDisplay 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IBindingDisplay.GetCurrentDisplay
api_location: diasymreader.dll
api_type: COM
f1_keywords: IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4e9ba86efe44fdcfb717970bf664198068d89d36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="96bfb-102">IBindingDisplay::GetCurrentDisplay 方法</span><span class="sxs-lookup"><span data-stu-id="96bfb-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="96bfb-103">返回当前绑定的显示信息。</span><span class="sxs-lookup"><span data-stu-id="96bfb-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96bfb-104">语法</span><span class="sxs-lookup"><span data-stu-id="96bfb-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96bfb-105">参数</span><span class="sxs-lookup"><span data-stu-id="96bfb-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="96bfb-106">[out，retval]指向 safearray 包含绑定显示信息的指针。</span><span class="sxs-lookup"><span data-stu-id="96bfb-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96bfb-107">备注</span><span class="sxs-lookup"><span data-stu-id="96bfb-107">Remarks</span></span>  
 <span data-ttu-id="96bfb-108">[Ibindingdisplay:: Initializeforprocess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)方法必须具有以前成功，并且必须由调试器停止程序。</span><span class="sxs-lookup"><span data-stu-id="96bfb-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="96bfb-109">调用方必须释放返回`SAFEARRAY`使用的内存[SafeArrayDestroy](http://msdn.microsoft.com/en-us/fc94f7e7-b903-4c78-905c-54df1f8d13fa)。</span><span class="sxs-lookup"><span data-stu-id="96bfb-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](http://msdn.microsoft.com/en-us/fc94f7e7-b903-4c78-905c-54df1f8d13fa).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96bfb-110">要求</span><span class="sxs-lookup"><span data-stu-id="96bfb-110">Requirements</span></span>  
 <span data-ttu-id="96bfb-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="96bfb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96bfb-112">**标头：** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="96bfb-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="96bfb-113">**库：** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="96bfb-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="96bfb-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96bfb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96bfb-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96bfb-115">See Also</span></span>  
 [<span data-ttu-id="96bfb-116">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="96bfb-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 [<span data-ttu-id="96bfb-117">InitializeForProcess 方法</span><span class="sxs-lookup"><span data-stu-id="96bfb-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
