---
title: IMetaDataEmit::DefineParam 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d49ac70aceb76f69711ea4bf514f69697ac156c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447367"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="bb9c1-102">IMetaDataEmit::DefineParam 方法</span><span class="sxs-lookup"><span data-stu-id="bb9c1-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="bb9c1-103">使用指定的签名与指定标记引用的方法创建的参数定义并获取该参数定义的标记。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb9c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb9c1-104">Syntax</span></span>  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb9c1-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb9c1-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="bb9c1-106">[in]正在定义中其参数的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="bb9c1-107">[in]参数序列号。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="bb9c1-108">[in]以 Unicode 参数的名称。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="bb9c1-109">[in]参数的的标志。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="bb9c1-110">这是一个位掩码的`CorParamAttr`值。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="bb9c1-111">[in]`ELEMENT_TYPE_` *\** 的常量值。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="bb9c1-112">[in]参数的常量值。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="bb9c1-113">[in]大小，以 Unicode 字符的`pValue`。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="bb9c1-114">[out]`mdParamDef`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb9c1-115">备注</span><span class="sxs-lookup"><span data-stu-id="bb9c1-115">Remarks</span></span>  
 <span data-ttu-id="bb9c1-116">序列值在`ulParamSeq`开头的参数 1。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="bb9c1-117">返回值具有序列号为 0。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb9c1-118">要求</span><span class="sxs-lookup"><span data-stu-id="bb9c1-118">Requirements</span></span>  
 <span data-ttu-id="bb9c1-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb9c1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb9c1-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb9c1-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb9c1-121">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bb9c1-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb9c1-122">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9c1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9c1-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb9c1-123">See Also</span></span>  
 [<span data-ttu-id="bb9c1-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="bb9c1-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="bb9c1-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="bb9c1-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
