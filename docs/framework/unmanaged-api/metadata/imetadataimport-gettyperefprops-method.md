---
title: "IMetaDataImport::GetTypeRefProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 23dbfe2468088da5e02fb7156606af5f3fa51044
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="ca2ad-102">IMetaDataImport::GetTypeRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="ca2ad-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="ca2ad-103">获取与关联的元数据<xref:System.Type>指定的 TypeRef 标记所引用。</span><span class="sxs-lookup"><span data-stu-id="ca2ad-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca2ad-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca2ad-104">Syntax</span></span>  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca2ad-105">参数</span><span class="sxs-lookup"><span data-stu-id="ca2ad-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="ca2ad-106">[in]表示要返回的元数据的类型的 TypeRef 标记。</span><span class="sxs-lookup"><span data-stu-id="ca2ad-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="ca2ad-107">[out]指向在其中进行引用的作用域的指针。</span><span class="sxs-lookup"><span data-stu-id="ca2ad-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="ca2ad-108">此值是 AssemblyRef 或 ModuleRef 标记。</span><span class="sxs-lookup"><span data-stu-id="ca2ad-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="ca2ad-109">[out]包含的类型名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ca2ad-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ca2ad-110">[in]请求的大小以宽字符为单位`szName`。</span><span class="sxs-lookup"><span data-stu-id="ca2ad-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ca2ad-111">[out]在宽字符为单位返回的大小`szName`。</span><span class="sxs-lookup"><span data-stu-id="ca2ad-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca2ad-112">惠?</span><span class="sxs-lookup"><span data-stu-id="ca2ad-112">Requirements</span></span>  
 <span data-ttu-id="ca2ad-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca2ad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca2ad-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ca2ad-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca2ad-115">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ca2ad-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca2ad-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca2ad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca2ad-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca2ad-117">See Also</span></span>  
 [<span data-ttu-id="ca2ad-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="ca2ad-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ca2ad-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="ca2ad-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
