---
title: CreateAssemblyCache 函数
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5869bf22c74a232f20fc49fe81a6a35c9738f1db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735008"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="a7e16-102">CreateAssemblyCache 函数</span><span class="sxs-lookup"><span data-stu-id="a7e16-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="a7e16-103">获取一个指向到新[IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)实例，它表示全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="a7e16-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e16-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7e16-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7e16-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7e16-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="a7e16-106">[out]返回`IAssemblyCache`指针。</span><span class="sxs-lookup"><span data-stu-id="a7e16-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="a7e16-107">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="a7e16-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a7e16-108">`dwReserved` 必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="a7e16-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7e16-109">要求</span><span class="sxs-lookup"><span data-stu-id="a7e16-109">Requirements</span></span>  
 <span data-ttu-id="a7e16-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e16-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7e16-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a7e16-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a7e16-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a7e16-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7e16-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7e16-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e16-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7e16-114">See also</span></span>
- [<span data-ttu-id="a7e16-115">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="a7e16-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="a7e16-116">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="a7e16-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="a7e16-117">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="a7e16-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
