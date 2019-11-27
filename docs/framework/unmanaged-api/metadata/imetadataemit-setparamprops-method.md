---
title: IMetaDataEmit::SetParamProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: 813460aa027b259866b168d426fd28502b5c4465
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432494"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="26054-102">IMetaDataEmit::SetParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="26054-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="26054-103">设置或更改之前调用[IMetaDataEmit：:D efineparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)时定义的方法参数的功能。</span><span class="sxs-lookup"><span data-stu-id="26054-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26054-104">语法</span><span class="sxs-lookup"><span data-stu-id="26054-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26054-105">参数</span><span class="sxs-lookup"><span data-stu-id="26054-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="26054-106">中目标参数的标记。</span><span class="sxs-lookup"><span data-stu-id="26054-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="26054-107">中Unicode 中参数的名称。</span><span class="sxs-lookup"><span data-stu-id="26054-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="26054-108">中参数的标志。</span><span class="sxs-lookup"><span data-stu-id="26054-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="26054-109">中常量值的 ELEMENT_TYPE_ \*。</span><span class="sxs-lookup"><span data-stu-id="26054-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="26054-110">中参数的常数值。</span><span class="sxs-lookup"><span data-stu-id="26054-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="26054-111">中`pValue`的大小（Unicode）字符。</span><span class="sxs-lookup"><span data-stu-id="26054-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26054-112">要求</span><span class="sxs-lookup"><span data-stu-id="26054-112">Requirements</span></span>  
 <span data-ttu-id="26054-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26054-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26054-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="26054-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26054-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="26054-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26054-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26054-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26054-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26054-117">See also</span></span>

- [<span data-ttu-id="26054-118">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="26054-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="26054-119">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="26054-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
