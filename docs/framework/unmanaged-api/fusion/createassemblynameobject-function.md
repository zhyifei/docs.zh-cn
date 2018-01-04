---
title: "CreateAssemblyNameObject 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyNameObject
helpviewer_keywords: CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d2616bd7aee878ebbc1d196cb1ac5f90ae7bd04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="e7e8a-102">CreateAssemblyNameObject 函数</span><span class="sxs-lookup"><span data-stu-id="e7e8a-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="e7e8a-103">获取到的接口指针[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)表示具有指定名称的程序集的唯一标识的实例。</span><span class="sxs-lookup"><span data-stu-id="e7e8a-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e8a-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7e8a-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7e8a-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7e8a-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="e7e8a-106">[out]返回`IAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="e7e8a-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="e7e8a-107">[in]要为其创建新程序集的名称`IAssemblyName`实例。</span><span class="sxs-lookup"><span data-stu-id="e7e8a-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e7e8a-108">[in]要传递给对象构造函数的标志。</span><span class="sxs-lookup"><span data-stu-id="e7e8a-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e7e8a-109">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="e7e8a-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e7e8a-110">`pvReserved`必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="e7e8a-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e8a-111">惠?</span><span class="sxs-lookup"><span data-stu-id="e7e8a-111">Requirements</span></span>  
 <span data-ttu-id="e7e8a-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e8a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e8a-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e7e8a-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e7e8a-114">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e7e8a-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7e8a-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e8a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e8a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7e8a-116">See Also</span></span>  
 [<span data-ttu-id="e7e8a-117">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="e7e8a-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="e7e8a-118">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="e7e8a-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
