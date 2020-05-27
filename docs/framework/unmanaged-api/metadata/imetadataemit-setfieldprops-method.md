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
ms.openlocfilehash: 220556ec130c7bff7c413405820c4fee0582b051
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008009"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="f8ea5-102">IMetaDataEmit::SetFieldProps 方法</span><span class="sxs-lookup"><span data-stu-id="f8ea5-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="f8ea5-103">设置或更新指定字段标记所引用的字段的默认值。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8ea5-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8ea5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8ea5-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8ea5-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="f8ea5-106">中目标字段的标记。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="f8ea5-107">中字段特性。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-107">[in] Field attributes.</span></span> <span data-ttu-id="f8ea5-108">这是一个值的位掩码 `CorFieldAttr` 。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="f8ea5-109">中`ELEMENT_TYPE_` *\** 常数值的。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="f8ea5-110">这是一个 `CorElementType` 值。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="f8ea5-111">如果未定义常数，请将此值设置为 `ELEMENT_TYPE_END` 。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f8ea5-112">中字段的常数值。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="f8ea5-113">中的大小（以 Unicode 字符为格式） `pValue` 。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8ea5-114">要求</span><span class="sxs-lookup"><span data-stu-id="f8ea5-114">Requirements</span></span>  
 <span data-ttu-id="f8ea5-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8ea5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8ea5-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f8ea5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8ea5-117">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f8ea5-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8ea5-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8ea5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ea5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8ea5-119">See also</span></span>

- [<span data-ttu-id="f8ea5-120">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="f8ea5-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f8ea5-121">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="f8ea5-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
