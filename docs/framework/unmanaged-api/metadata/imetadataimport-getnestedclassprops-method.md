---
title: IMetaDataImport::GetNestedClassProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb5820087001a207af0c2552f91b4c17f5f78ff7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074828"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="66fc4-102">IMetaDataImport::GetNestedClassProps 方法</span><span class="sxs-lookup"><span data-stu-id="66fc4-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="66fc4-103">获取父标记 TypeDef<xref:System.Type>指定的嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="66fc4-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66fc4-104">语法</span><span class="sxs-lookup"><span data-stu-id="66fc4-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66fc4-105">参数</span><span class="sxs-lookup"><span data-stu-id="66fc4-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="66fc4-106">[in]一个 TypeDef 令牌表示<xref:System.Type>要返回的父类的令牌。</span><span class="sxs-lookup"><span data-stu-id="66fc4-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="66fc4-107">[out]指向的 TypeDef 标记的指针<xref:System.Type>的`tdNestedClass`嵌套在中。</span><span class="sxs-lookup"><span data-stu-id="66fc4-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66fc4-108">要求</span><span class="sxs-lookup"><span data-stu-id="66fc4-108">Requirements</span></span>  
 <span data-ttu-id="66fc4-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="66fc4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66fc4-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="66fc4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66fc4-111">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="66fc4-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="66fc4-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="66fc4-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66fc4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="66fc4-113">See also</span></span>

- [<span data-ttu-id="66fc4-114">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="66fc4-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="66fc4-115">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="66fc4-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
