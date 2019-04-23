---
title: IMetaDataImport::IsGlobal 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b956ac1717ffcb73e819e985450249754f80af2a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136157"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="39bb9-102">IMetaDataImport::IsGlobal 方法</span><span class="sxs-lookup"><span data-stu-id="39bb9-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="39bb9-103">获取一个值，该值指示由指定的元数据标记表示的字段、方法或类型是否具有全局范围。</span><span class="sxs-lookup"><span data-stu-id="39bb9-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39bb9-104">语法</span><span class="sxs-lookup"><span data-stu-id="39bb9-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39bb9-105">参数</span><span class="sxs-lookup"><span data-stu-id="39bb9-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="39bb9-106">[in]表示类型、 字段或方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="39bb9-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="39bb9-107">[out] 1，如果该对象具有全局作用域;否则为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="39bb9-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39bb9-108">要求</span><span class="sxs-lookup"><span data-stu-id="39bb9-108">Requirements</span></span>  
 <span data-ttu-id="39bb9-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39bb9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39bb9-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="39bb9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39bb9-111">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="39bb9-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39bb9-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39bb9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bb9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="39bb9-113">See also</span></span>

- [<span data-ttu-id="39bb9-114">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="39bb9-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="39bb9-115">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="39bb9-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
