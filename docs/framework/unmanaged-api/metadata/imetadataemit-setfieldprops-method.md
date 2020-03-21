---
title: IMetaDataEmit::SetFieldProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: b921118f7c43edef3c07cbb34cbbd9119d36ce51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177556"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="7d3d7-102">IMetaDataEmit::SetFieldProps 方法</span><span class="sxs-lookup"><span data-stu-id="7d3d7-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="7d3d7-103">设置或更新指定字段令牌引用的字段的默认值。</span><span class="sxs-lookup"><span data-stu-id="7d3d7-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d3d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d3d7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d3d7-105">parameters</span><span class="sxs-lookup"><span data-stu-id="7d3d7-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="7d3d7-106">[在]目标字段的令牌。</span><span class="sxs-lookup"><span data-stu-id="7d3d7-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="7d3d7-107">[在]字段属性。</span><span class="sxs-lookup"><span data-stu-id="7d3d7-107">[in] Field attributes.</span></span> <span data-ttu-id="7d3d7-108">这是值的`CorFieldAttr`位掩码。</span><span class="sxs-lookup"><span data-stu-id="7d3d7-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="7d3d7-109">[在]常`ELEMENT_TYPE_`*\** 量值的 。</span><span class="sxs-lookup"><span data-stu-id="7d3d7-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="7d3d7-110">这是一个`CorElementType`值。</span><span class="sxs-lookup"><span data-stu-id="7d3d7-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="7d3d7-111">如果未定义常量，则将此值设置为`ELEMENT_TYPE_END`。</span><span class="sxs-lookup"><span data-stu-id="7d3d7-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="7d3d7-112">[在]字段的常量值。</span><span class="sxs-lookup"><span data-stu-id="7d3d7-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="7d3d7-113">[在]的大小（以 Unicode 字符表示`pValue`）</span><span class="sxs-lookup"><span data-stu-id="7d3d7-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d3d7-114">要求</span><span class="sxs-lookup"><span data-stu-id="7d3d7-114">Requirements</span></span>  
 <span data-ttu-id="7d3d7-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d3d7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d3d7-116">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="7d3d7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d3d7-117">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7d3d7-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d3d7-118">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d3d7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d3d7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d3d7-119">See also</span></span>

- [<span data-ttu-id="7d3d7-120">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="7d3d7-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7d3d7-121">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="7d3d7-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
