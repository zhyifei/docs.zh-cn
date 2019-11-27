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
ms.openlocfilehash: e73c95d8c720ed3263d6a66c48bdb5b5582eb686
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442179"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="4ad6c-102">IMetaDataDispenserEx::FindAssemblyModule 方法</span><span class="sxs-lookup"><span data-stu-id="4ad6c-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="4ad6c-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-103">This method is not implemented.</span></span> <span data-ttu-id="4ad6c-104">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad6c-105">语法</span><span class="sxs-lookup"><span data-stu-id="4ad6c-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="4ad6c-106">参数</span><span class="sxs-lookup"><span data-stu-id="4ad6c-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="4ad6c-107">中不使用。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="4ad6c-108">中不使用。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="4ad6c-109">中不使用。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="4ad6c-110">中模块的名称。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="4ad6c-111">中要查找的程序集。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="4ad6c-112">弄程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4ad6c-113">中`szName`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="4ad6c-114">弄`szName`中实际返回的字符数。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ad6c-115">要求</span><span class="sxs-lookup"><span data-stu-id="4ad6c-115">Requirements</span></span>  
 <span data-ttu-id="4ad6c-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4ad6c-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ad6c-117">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="4ad6c-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ad6c-118">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4ad6c-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ad6c-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ad6c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad6c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ad6c-120">See also</span></span>

- [<span data-ttu-id="4ad6c-121">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="4ad6c-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="4ad6c-122">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="4ad6c-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
