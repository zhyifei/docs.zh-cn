---
title: "_CorImageUnloading 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorImageUnloading
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorImageUnloading
helpviewer_keywords: _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90df58e2765cdecf4a1ec22cf5540e5cfa9530a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corimageunloading-function"></a><span data-ttu-id="f21fb-102">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="f21fb-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="f21fb-103">卸载托管的模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="f21fb-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="f21fb-104">未实现此函数。</span><span class="sxs-lookup"><span data-stu-id="f21fb-104">This function is not implemented.</span></span> <span data-ttu-id="f21fb-105">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="f21fb-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f21fb-106">语法</span><span class="sxs-lookup"><span data-stu-id="f21fb-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f21fb-107">参数</span><span class="sxs-lookup"><span data-stu-id="f21fb-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="f21fb-108">[in]指向要卸载的映像的起始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="f21fb-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f21fb-109">要求</span><span class="sxs-lookup"><span data-stu-id="f21fb-109">Requirements</span></span>  
 <span data-ttu-id="f21fb-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f21fb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f21fb-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f21fb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f21fb-112">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f21fb-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f21fb-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f21fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21fb-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f21fb-114">See Also</span></span>  
 [<span data-ttu-id="f21fb-115">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="f21fb-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
