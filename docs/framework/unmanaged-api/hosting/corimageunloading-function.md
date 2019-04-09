---
title: _CorImageUnloading 函数
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cb5f9decbcdfb71f67a5132dc59773f1de8b0a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086424"
---
# <a name="corimageunloading-function"></a><span data-ttu-id="47783-102">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="47783-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="47783-103">卸载托管的模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="47783-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="47783-104">未实现此函数。</span><span class="sxs-lookup"><span data-stu-id="47783-104">This function is not implemented.</span></span> <span data-ttu-id="47783-105">如果调用，则返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="47783-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47783-106">语法</span><span class="sxs-lookup"><span data-stu-id="47783-106">Syntax</span></span>  
  
```  
STDAPI (VOID) _CorImageUnloading(   
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47783-107">参数</span><span class="sxs-lookup"><span data-stu-id="47783-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="47783-108">[in]指向要卸载的图像的起始位置的指针。</span><span class="sxs-lookup"><span data-stu-id="47783-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47783-109">要求</span><span class="sxs-lookup"><span data-stu-id="47783-109">Requirements</span></span>  
 <span data-ttu-id="47783-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47783-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47783-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="47783-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47783-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="47783-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="47783-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="47783-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="47783-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="47783-114">See also</span></span>

- [<span data-ttu-id="47783-115">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="47783-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
