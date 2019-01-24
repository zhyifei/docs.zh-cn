---
title: IMetaDataDispenserEx::FindAssemblyModule 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ae455aeba353cfa66a1253b580e15b280caec8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584095"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="34ab3-102">IMetaDataDispenserEx::FindAssemblyModule 方法</span><span class="sxs-lookup"><span data-stu-id="34ab3-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="34ab3-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="34ab3-103">This method is not implemented.</span></span> <span data-ttu-id="34ab3-104">如果调用，则返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="34ab3-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34ab3-105">语法</span><span class="sxs-lookup"><span data-stu-id="34ab3-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="34ab3-106">参数</span><span class="sxs-lookup"><span data-stu-id="34ab3-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="34ab3-107">[in]不使用。</span><span class="sxs-lookup"><span data-stu-id="34ab3-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="34ab3-108">[in]不使用。</span><span class="sxs-lookup"><span data-stu-id="34ab3-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="34ab3-109">[in]不使用。</span><span class="sxs-lookup"><span data-stu-id="34ab3-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="34ab3-110">[in]模块的名称。</span><span class="sxs-lookup"><span data-stu-id="34ab3-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="34ab3-111">[in]要找的程序集。</span><span class="sxs-lookup"><span data-stu-id="34ab3-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="34ab3-112">[out]程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="34ab3-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="34ab3-113">[in]大小，以字节为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="34ab3-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="34ab3-114">[out]中实际返回的字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="34ab3-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34ab3-115">要求</span><span class="sxs-lookup"><span data-stu-id="34ab3-115">Requirements</span></span>  
 <span data-ttu-id="34ab3-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34ab3-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34ab3-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34ab3-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34ab3-118">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="34ab3-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34ab3-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34ab3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ab3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="34ab3-120">See also</span></span>
- [<span data-ttu-id="34ab3-121">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="34ab3-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="34ab3-122">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="34ab3-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
