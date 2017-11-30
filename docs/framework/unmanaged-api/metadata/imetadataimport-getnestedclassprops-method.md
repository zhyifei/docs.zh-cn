---
title: "IMetaDataImport::GetNestedClassProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNestedClassProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a538cea5267b32790a9c656df9584d5ea31f54c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="248f2-102">IMetaDataImport::GetNestedClassProps 方法</span><span class="sxs-lookup"><span data-stu-id="248f2-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="248f2-103">获取的 TypeDef 标记的父<xref:System.Type>指定嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="248f2-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="248f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="248f2-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="248f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="248f2-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="248f2-106">[in]一个 TypeDef 令牌表示<xref:System.Type>要返回的父类的令牌。</span><span class="sxs-lookup"><span data-stu-id="248f2-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="248f2-107">[out]TypeDef 标记的指针<xref:System.Type>，`tdNestedClass`嵌套在。</span><span class="sxs-lookup"><span data-stu-id="248f2-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="248f2-108">要求</span><span class="sxs-lookup"><span data-stu-id="248f2-108">Requirements</span></span>  
 <span data-ttu-id="248f2-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="248f2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="248f2-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="248f2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="248f2-111">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="248f2-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="248f2-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="248f2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="248f2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="248f2-113">See Also</span></span>  
 [<span data-ttu-id="248f2-114">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="248f2-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="248f2-115">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="248f2-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
