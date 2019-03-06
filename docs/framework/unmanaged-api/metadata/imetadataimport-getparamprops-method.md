---
title: IMetaDataImport::GetParamProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ed9bae4fde96f0878e40ed73b81cc8776571ada5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468053"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="3a674-102">IMetaDataImport::GetParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="3a674-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="3a674-103">获取指定的 ParamDef 标记所引用的参数的元数据值。</span><span class="sxs-lookup"><span data-stu-id="3a674-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a674-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a674-104">Syntax</span></span>  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a674-105">参数</span><span class="sxs-lookup"><span data-stu-id="3a674-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3a674-106">[in]表示要返回的元数据的参数的 ParamDef 标记。</span><span class="sxs-lookup"><span data-stu-id="3a674-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="3a674-107">[out]指向表示采用参数的方法的 MethodDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="3a674-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="3a674-108">[out]参数的方法参数列表中的序号位置。</span><span class="sxs-lookup"><span data-stu-id="3a674-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="3a674-109">[out]用于保存参数的名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3a674-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3a674-110">[in]请求的大小以宽字符为单位`szName`。</span><span class="sxs-lookup"><span data-stu-id="3a674-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="3a674-111">[out]在宽字符为单位返回的大小`szName`。</span><span class="sxs-lookup"><span data-stu-id="3a674-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="3a674-112">[out]一个指向任何与参数关联的特性标志。</span><span class="sxs-lookup"><span data-stu-id="3a674-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="3a674-113">这是一个位掩码的`CorParamAttr`值。</span><span class="sxs-lookup"><span data-stu-id="3a674-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="3a674-114">[out]该参数是指向一个标志，用于指定的指针<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="3a674-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="3a674-115">[out]指向常量字符串的参数返回的指针。</span><span class="sxs-lookup"><span data-stu-id="3a674-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="3a674-116">[out]大小`ppValue`宽字符，或者，如果零`ppValue`不保存字符串。</span><span class="sxs-lookup"><span data-stu-id="3a674-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a674-117">备注</span><span class="sxs-lookup"><span data-stu-id="3a674-117">Remarks</span></span>

<span data-ttu-id="3a674-118">中的顺序值`pulSequence`参数 1 开头。</span><span class="sxs-lookup"><span data-stu-id="3a674-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="3a674-119">返回值具有的序列号为 0。</span><span class="sxs-lookup"><span data-stu-id="3a674-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a674-120">要求</span><span class="sxs-lookup"><span data-stu-id="3a674-120">Requirements</span></span>  
 <span data-ttu-id="3a674-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3a674-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a674-122">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3a674-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a674-123">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3a674-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a674-124">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a674-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a674-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a674-125">See also</span></span>
- [<span data-ttu-id="3a674-126">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3a674-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3a674-127">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3a674-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
