---
title: "IMetaDataDispenserEx::FindAssembly 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.FindAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a70d1e2b3636a405fe28b84c2e76dd7264df4f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="2e66e-102">IMetaDataDispenserEx::FindAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="2e66e-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="2e66e-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="2e66e-103">This method is not implemented.</span></span> <span data-ttu-id="2e66e-104">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="2e66e-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e66e-105">语法</span><span class="sxs-lookup"><span data-stu-id="2e66e-105">Syntax</span></span>  
  
```  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e66e-106">参数</span><span class="sxs-lookup"><span data-stu-id="2e66e-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="2e66e-107">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="2e66e-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="2e66e-108">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="2e66e-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="2e66e-109">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="2e66e-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="2e66e-110">[in]要找的程序集。</span><span class="sxs-lookup"><span data-stu-id="2e66e-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="2e66e-111">[out]程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="2e66e-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2e66e-112">[in]大小，以字节为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="2e66e-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="2e66e-113">[out]中实际返回的字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="2e66e-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e66e-114">要求</span><span class="sxs-lookup"><span data-stu-id="2e66e-114">Requirements</span></span>  
 <span data-ttu-id="2e66e-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e66e-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e66e-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e66e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e66e-117">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2e66e-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2e66e-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e66e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e66e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e66e-119">See Also</span></span>  
 [<span data-ttu-id="2e66e-120">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="2e66e-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="2e66e-121">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="2e66e-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
