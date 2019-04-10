---
title: IMetaDataImport::FindTypeDefByName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5cd6b74ce2871cfafc0dc2260be3f758f6a28704
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168683"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="52eed-102">IMetaDataImport::FindTypeDefByName 方法</span><span class="sxs-lookup"><span data-stu-id="52eed-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="52eed-103">获取一个指向的 TypeDef 元数据标记为<xref:System.Type>具有指定名称。</span><span class="sxs-lookup"><span data-stu-id="52eed-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52eed-104">语法</span><span class="sxs-lookup"><span data-stu-id="52eed-104">Syntax</span></span>  
  
```  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52eed-105">参数</span><span class="sxs-lookup"><span data-stu-id="52eed-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="52eed-106">[in]要为其获取 TypeDef 令牌类型的名称。</span><span class="sxs-lookup"><span data-stu-id="52eed-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="52eed-107">[in]表示在封闭类的 TypeDef 或 TypeRef 标记。</span><span class="sxs-lookup"><span data-stu-id="52eed-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="52eed-108">如果要查找的类型不是嵌套的类，此值设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="52eed-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="52eed-109">[out]指向匹配的 TypeDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="52eed-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52eed-110">要求</span><span class="sxs-lookup"><span data-stu-id="52eed-110">Requirements</span></span>  
 <span data-ttu-id="52eed-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52eed-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52eed-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="52eed-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52eed-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="52eed-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="52eed-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="52eed-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="52eed-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="52eed-115">See also</span></span>

- [<span data-ttu-id="52eed-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="52eed-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="52eed-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="52eed-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
