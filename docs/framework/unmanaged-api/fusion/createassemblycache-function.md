---
title: "CreateAssemblyCache 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5e730ea9f83a40d92cb6a865fcdd87ebf523fe7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createassemblycache-function"></a><span data-ttu-id="c6df8-102">CreateAssemblyCache 函数</span><span class="sxs-lookup"><span data-stu-id="c6df8-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="c6df8-103">获取一个指针，到新[IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)表示全局程序集缓存的实例。</span><span class="sxs-lookup"><span data-stu-id="c6df8-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6df8-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6df8-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6df8-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6df8-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="c6df8-106">[out]返回`IAssemblyCache`指针。</span><span class="sxs-lookup"><span data-stu-id="c6df8-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="c6df8-107">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="c6df8-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c6df8-108">`dwReserved`必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="c6df8-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6df8-109">惠?</span><span class="sxs-lookup"><span data-stu-id="c6df8-109">Requirements</span></span>  
 <span data-ttu-id="c6df8-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6df8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6df8-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c6df8-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c6df8-112">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c6df8-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6df8-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6df8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6df8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6df8-114">See Also</span></span>  
 [<span data-ttu-id="c6df8-115">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="c6df8-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="c6df8-116">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="c6df8-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="c6df8-117">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="c6df8-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
