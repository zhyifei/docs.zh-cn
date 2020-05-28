---
title: IMetaDataDispenserEx::FindAssembly 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: 50aebb09924b93a622e5b7d84e65e41ee91f6018
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006189"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="86d9b-102">IMetaDataDispenserEx::FindAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="86d9b-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="86d9b-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="86d9b-103">This method is not implemented.</span></span> <span data-ttu-id="86d9b-104">如果调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="86d9b-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86d9b-105">语法</span><span class="sxs-lookup"><span data-stu-id="86d9b-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="86d9b-106">参数</span><span class="sxs-lookup"><span data-stu-id="86d9b-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="86d9b-107">中不使用。</span><span class="sxs-lookup"><span data-stu-id="86d9b-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="86d9b-108">中不使用。</span><span class="sxs-lookup"><span data-stu-id="86d9b-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="86d9b-109">中不使用。</span><span class="sxs-lookup"><span data-stu-id="86d9b-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="86d9b-110">中要查找的程序集。</span><span class="sxs-lookup"><span data-stu-id="86d9b-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="86d9b-111">弄程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="86d9b-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="86d9b-112">中的大小（以字节为单位） `szName` 。</span><span class="sxs-lookup"><span data-stu-id="86d9b-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="86d9b-113">弄中实际返回的字符数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="86d9b-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86d9b-114">要求</span><span class="sxs-lookup"><span data-stu-id="86d9b-114">Requirements</span></span>  
 <span data-ttu-id="86d9b-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86d9b-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86d9b-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="86d9b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86d9b-117">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="86d9b-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86d9b-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86d9b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d9b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86d9b-119">See also</span></span>

- [<span data-ttu-id="86d9b-120">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="86d9b-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="86d9b-121">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="86d9b-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
