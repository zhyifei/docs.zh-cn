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
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177697"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="7e2dc-102">IMetaDataEmit::DefineParam 方法</span><span class="sxs-lookup"><span data-stu-id="7e2dc-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="7e2dc-103">为指定令牌引用的方法创建具有指定签名的参数定义，并获取该参数定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e2dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="7e2dc-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="7e2dc-105">parameters</span><span class="sxs-lookup"><span data-stu-id="7e2dc-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="7e2dc-106">[在]正在定义其参数的方法的令牌。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="7e2dc-107">[在]参数序列号。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="7e2dc-108">[在]Unicode 中参数的名称。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="7e2dc-109">[在]参数的标志。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="7e2dc-110">这是值的`CorParamAttr`位掩码。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="7e2dc-111">[在]`ELEMENT_TYPE_` *\**</span><span class="sxs-lookup"><span data-stu-id="7e2dc-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="7e2dc-112">[在]参数的常量值。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="7e2dc-113">[在]的大小（以 Unicode 字符表示`pValue`）</span><span class="sxs-lookup"><span data-stu-id="7e2dc-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="7e2dc-114">[出]分配的`mdParamDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e2dc-115">备注</span><span class="sxs-lookup"><span data-stu-id="7e2dc-115">Remarks</span></span>  
 <span data-ttu-id="7e2dc-116">中的序列值以`ulParamSeq`1 开头的参数。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="7e2dc-117">返回值的序列号为 0。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e2dc-118">要求</span><span class="sxs-lookup"><span data-stu-id="7e2dc-118">Requirements</span></span>  
 <span data-ttu-id="7e2dc-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e2dc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e2dc-120">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="7e2dc-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e2dc-121">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7e2dc-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e2dc-122">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e2dc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e2dc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e2dc-123">See also</span></span>

- [<span data-ttu-id="7e2dc-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="7e2dc-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7e2dc-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="7e2dc-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
