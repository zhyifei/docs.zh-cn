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
ms.openlocfilehash: efc627619d9abf9cfa6010e1c0ca709989b9cad3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445461"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="8f15a-102">IMetaDataEmit::SetFieldProps 方法</span><span class="sxs-lookup"><span data-stu-id="8f15a-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="8f15a-103">设置或更新指定字段标记所引用的字段的默认值。</span><span class="sxs-lookup"><span data-stu-id="8f15a-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f15a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f15a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f15a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8f15a-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="8f15a-106">中目标字段的标记。</span><span class="sxs-lookup"><span data-stu-id="8f15a-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="8f15a-107">中字段特性。</span><span class="sxs-lookup"><span data-stu-id="8f15a-107">[in] Field attributes.</span></span> <span data-ttu-id="8f15a-108">这是 `CorFieldAttr` 值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="8f15a-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="8f15a-109">中常量值的 `ELEMENT_TYPE_` *\** 。</span><span class="sxs-lookup"><span data-stu-id="8f15a-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="8f15a-110">这是 `CorElementType` 值。</span><span class="sxs-lookup"><span data-stu-id="8f15a-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="8f15a-111">如果未定义常数，请将此值设置为 `ELEMENT_TYPE_END`。</span><span class="sxs-lookup"><span data-stu-id="8f15a-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8f15a-112">中字段的常数值。</span><span class="sxs-lookup"><span data-stu-id="8f15a-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="8f15a-113">中`pValue`的大小（以 Unicode 字符为格式）。</span><span class="sxs-lookup"><span data-stu-id="8f15a-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f15a-114">要求</span><span class="sxs-lookup"><span data-stu-id="8f15a-114">Requirements</span></span>  
 <span data-ttu-id="8f15a-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f15a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f15a-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8f15a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f15a-117">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8f15a-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f15a-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f15a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f15a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f15a-119">See also</span></span>

- [<span data-ttu-id="8f15a-120">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="8f15a-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8f15a-121">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="8f15a-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
