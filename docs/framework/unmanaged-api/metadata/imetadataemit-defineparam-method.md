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
ms.openlocfilehash: 5384dd69578dbd912690b9490bd4bfa762ccd56d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475302"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="51cd9-102">IMetaDataEmit::DefineParam 方法</span><span class="sxs-lookup"><span data-stu-id="51cd9-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="51cd9-103">创建具有指定的签名为指定的标记所引用的方法的参数定义，并为该参数定义中获取的标记。</span><span class="sxs-lookup"><span data-stu-id="51cd9-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51cd9-104">语法</span><span class="sxs-lookup"><span data-stu-id="51cd9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="51cd9-105">参数</span><span class="sxs-lookup"><span data-stu-id="51cd9-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="51cd9-106">[in]要定义其参数的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="51cd9-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="51cd9-107">[in]参数序列号。</span><span class="sxs-lookup"><span data-stu-id="51cd9-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="51cd9-108">[in]以 unicode 格式参数的名称。</span><span class="sxs-lookup"><span data-stu-id="51cd9-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="51cd9-109">[in]参数的的标志。</span><span class="sxs-lookup"><span data-stu-id="51cd9-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="51cd9-110">这是一个位掩码的`CorParamAttr`值。</span><span class="sxs-lookup"><span data-stu-id="51cd9-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="51cd9-111">[in]`ELEMENT_TYPE_` *\** 的常量值。</span><span class="sxs-lookup"><span data-stu-id="51cd9-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="51cd9-112">[in]参数的常量值。</span><span class="sxs-lookup"><span data-stu-id="51cd9-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="51cd9-113">[in]大小，以 Unicode 字符的`pValue`。</span><span class="sxs-lookup"><span data-stu-id="51cd9-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="51cd9-114">[out]`mdParamDef`分配标记。</span><span class="sxs-lookup"><span data-stu-id="51cd9-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51cd9-115">备注</span><span class="sxs-lookup"><span data-stu-id="51cd9-115">Remarks</span></span>  
 <span data-ttu-id="51cd9-116">中的顺序值`ulParamSeq`参数 1 开头。</span><span class="sxs-lookup"><span data-stu-id="51cd9-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="51cd9-117">返回值具有的序列号为 0。</span><span class="sxs-lookup"><span data-stu-id="51cd9-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51cd9-118">要求</span><span class="sxs-lookup"><span data-stu-id="51cd9-118">Requirements</span></span>  
 <span data-ttu-id="51cd9-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51cd9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51cd9-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="51cd9-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51cd9-121">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="51cd9-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51cd9-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51cd9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51cd9-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="51cd9-123">See also</span></span>
- [<span data-ttu-id="51cd9-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="51cd9-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="51cd9-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="51cd9-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
