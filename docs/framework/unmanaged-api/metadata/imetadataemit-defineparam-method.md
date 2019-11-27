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
ms.openlocfilehash: 5c81bc82e19bce658336e4860a61f2721e17423d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431688"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="f632b-102">IMetaDataEmit::DefineParam 方法</span><span class="sxs-lookup"><span data-stu-id="f632b-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="f632b-103">创建具有指定标记所引用的方法的指定签名的参数定义，并获取该参数定义的标记。</span><span class="sxs-lookup"><span data-stu-id="f632b-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f632b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f632b-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f632b-105">参数</span><span class="sxs-lookup"><span data-stu-id="f632b-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="f632b-106">中正在定义其参数的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="f632b-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="f632b-107">中参数序列号。</span><span class="sxs-lookup"><span data-stu-id="f632b-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="f632b-108">中Unicode 中参数的名称。</span><span class="sxs-lookup"><span data-stu-id="f632b-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="f632b-109">中参数的标志。</span><span class="sxs-lookup"><span data-stu-id="f632b-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="f632b-110">这是 `CorParamAttr` 值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f632b-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="f632b-111">[in] `ELEMENT_TYPE_`常量值的 *\** 。</span><span class="sxs-lookup"><span data-stu-id="f632b-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f632b-112">中参数的常数值。</span><span class="sxs-lookup"><span data-stu-id="f632b-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="f632b-113">中`pValue`的大小（以 Unicode 字符为格式）。</span><span class="sxs-lookup"><span data-stu-id="f632b-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="f632b-114">弄分配 `mdParamDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="f632b-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f632b-115">备注</span><span class="sxs-lookup"><span data-stu-id="f632b-115">Remarks</span></span>  
 <span data-ttu-id="f632b-116">对于参数，`ulParamSeq` 中的序列值从1开始。</span><span class="sxs-lookup"><span data-stu-id="f632b-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="f632b-117">返回值的序列号为0。</span><span class="sxs-lookup"><span data-stu-id="f632b-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f632b-118">要求</span><span class="sxs-lookup"><span data-stu-id="f632b-118">Requirements</span></span>  
 <span data-ttu-id="f632b-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f632b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f632b-120">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f632b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f632b-121">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f632b-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f632b-122">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f632b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f632b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f632b-123">See also</span></span>

- [<span data-ttu-id="f632b-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f632b-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f632b-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="f632b-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
