---
title: "IMetaDataImport::FindTypeDefByName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindTypeDefByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4b3a5f9ff15e2b94e6d5c5e885605d8eabae711
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="7b65b-102">IMetaDataImport::FindTypeDefByName 方法</span><span class="sxs-lookup"><span data-stu-id="7b65b-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="7b65b-103">获取一个指向的 TypeDef 元数据标记为<xref:System.Type>具有指定名称。</span><span class="sxs-lookup"><span data-stu-id="7b65b-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b65b-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b65b-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b65b-105">参数</span><span class="sxs-lookup"><span data-stu-id="7b65b-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="7b65b-106">[in]要为其获取 TypeDef 令牌类型的名称。</span><span class="sxs-lookup"><span data-stu-id="7b65b-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="7b65b-107">[in]表示在封闭类的 TypeDef 或 TypeRef 标记。</span><span class="sxs-lookup"><span data-stu-id="7b65b-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="7b65b-108">如果要查找的类型不是嵌套的类，则将此值设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7b65b-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="7b65b-109">[out]指向匹配的 TypeDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="7b65b-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b65b-110">要求</span><span class="sxs-lookup"><span data-stu-id="7b65b-110">Requirements</span></span>  
 <span data-ttu-id="7b65b-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b65b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b65b-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b65b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b65b-113">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7b65b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b65b-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b65b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b65b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b65b-115">See Also</span></span>  
 [<span data-ttu-id="7b65b-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7b65b-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7b65b-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7b65b-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
