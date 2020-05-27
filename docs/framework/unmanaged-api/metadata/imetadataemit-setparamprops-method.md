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
ms.openlocfilehash: b710f966f519e2702607b7e186fff5986110d391
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007814"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="817ac-102">IMetaDataEmit::SetParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="817ac-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="817ac-103">设置或更改之前调用[IMetaDataEmit：:D efineparam](imetadataemit-defineparam-method.md)时定义的方法参数的功能。</span><span class="sxs-lookup"><span data-stu-id="817ac-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="817ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="817ac-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="817ac-105">参数</span><span class="sxs-lookup"><span data-stu-id="817ac-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="817ac-106">中目标参数的标记。</span><span class="sxs-lookup"><span data-stu-id="817ac-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="817ac-107">中Unicode 中参数的名称。</span><span class="sxs-lookup"><span data-stu-id="817ac-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="817ac-108">中参数的标志。</span><span class="sxs-lookup"><span data-stu-id="817ac-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="817ac-109">中常量值的 ELEMENT_TYPE_ \*。</span><span class="sxs-lookup"><span data-stu-id="817ac-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="817ac-110">中参数的常数值。</span><span class="sxs-lookup"><span data-stu-id="817ac-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="817ac-111">中的大小（Unicode）字符 `pValue` 。</span><span class="sxs-lookup"><span data-stu-id="817ac-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="817ac-112">要求</span><span class="sxs-lookup"><span data-stu-id="817ac-112">Requirements</span></span>  
 <span data-ttu-id="817ac-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="817ac-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="817ac-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="817ac-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="817ac-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="817ac-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="817ac-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="817ac-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="817ac-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="817ac-117">See also</span></span>

- [<span data-ttu-id="817ac-118">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="817ac-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="817ac-119">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="817ac-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
