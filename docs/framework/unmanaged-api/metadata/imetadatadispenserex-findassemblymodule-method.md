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
ms.openlocfilehash: 2d1d97e443be884f45187a2811ddfce106249515
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183126"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="10957-102">IMetaDataDispenserEx::FindAssemblyModule 方法</span><span class="sxs-lookup"><span data-stu-id="10957-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="10957-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="10957-103">This method is not implemented.</span></span> <span data-ttu-id="10957-104">如果调用，则返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="10957-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10957-105">语法</span><span class="sxs-lookup"><span data-stu-id="10957-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="10957-106">参数</span><span class="sxs-lookup"><span data-stu-id="10957-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="10957-107">[in]不使用。</span><span class="sxs-lookup"><span data-stu-id="10957-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="10957-108">[in]不使用。</span><span class="sxs-lookup"><span data-stu-id="10957-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="10957-109">[in]不使用。</span><span class="sxs-lookup"><span data-stu-id="10957-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="10957-110">[in]模块的名称。</span><span class="sxs-lookup"><span data-stu-id="10957-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="10957-111">[in]要找的程序集。</span><span class="sxs-lookup"><span data-stu-id="10957-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="10957-112">[out]程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="10957-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="10957-113">[in]大小，以字节为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="10957-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="10957-114">[out]中实际返回的字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="10957-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10957-115">要求</span><span class="sxs-lookup"><span data-stu-id="10957-115">Requirements</span></span>  
 <span data-ttu-id="10957-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10957-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10957-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="10957-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10957-118">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="10957-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="10957-119">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="10957-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="10957-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="10957-120">See also</span></span>

- [<span data-ttu-id="10957-121">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="10957-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="10957-122">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="10957-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
