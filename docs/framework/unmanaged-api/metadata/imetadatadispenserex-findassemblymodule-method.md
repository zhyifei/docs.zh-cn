---
title: "IMetaDataDispenserEx::FindAssemblyModule 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.FindAssemblyModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3911eeb5f6ff8122c71f0c1df973c4636ad8b665
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="e705a-102">IMetaDataDispenserEx::FindAssemblyModule 方法</span><span class="sxs-lookup"><span data-stu-id="e705a-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="e705a-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="e705a-103">This method is not implemented.</span></span> <span data-ttu-id="e705a-104">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="e705a-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e705a-105">语法</span><span class="sxs-lookup"><span data-stu-id="e705a-105">Syntax</span></span>  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e705a-106">参数</span><span class="sxs-lookup"><span data-stu-id="e705a-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="e705a-107">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="e705a-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="e705a-108">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="e705a-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="e705a-109">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="e705a-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="e705a-110">[in]模块的名称。</span><span class="sxs-lookup"><span data-stu-id="e705a-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="e705a-111">[in]要找的程序集。</span><span class="sxs-lookup"><span data-stu-id="e705a-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="e705a-112">[out]程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="e705a-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e705a-113">[in]大小，以字节为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="e705a-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="e705a-114">[out]中实际返回的字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="e705a-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e705a-115">要求</span><span class="sxs-lookup"><span data-stu-id="e705a-115">Requirements</span></span>  
 <span data-ttu-id="e705a-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e705a-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e705a-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e705a-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e705a-118">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e705a-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e705a-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e705a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e705a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e705a-120">See Also</span></span>  
 [<span data-ttu-id="e705a-121">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="e705a-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="e705a-122">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="e705a-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
