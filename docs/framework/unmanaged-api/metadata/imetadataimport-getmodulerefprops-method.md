---
title: "IMetaDataImport::GetModuleRefProps 方法"
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
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ee230b691411c49ba4f0096d998ac229283fc02c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="4eca6-102">IMetaDataImport::GetModuleRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="4eca6-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="4eca6-103">获取指定元数据标记引用的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="4eca6-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eca6-104">语法</span><span class="sxs-lookup"><span data-stu-id="4eca6-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4eca6-105">参数</span><span class="sxs-lookup"><span data-stu-id="4eca6-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="4eca6-106">[in]引用要获取的元数据信息的模块的 ModuleRef 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="4eca6-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="4eca6-107">[out]一个缓冲区来容纳模块名。</span><span class="sxs-lookup"><span data-stu-id="4eca6-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4eca6-108">[in]请求的大小的`szName`以宽字符为单位。</span><span class="sxs-lookup"><span data-stu-id="4eca6-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="4eca6-109">[out]返回的大小的`szName`以宽字符为单位。</span><span class="sxs-lookup"><span data-stu-id="4eca6-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eca6-110">惠?</span><span class="sxs-lookup"><span data-stu-id="4eca6-110">Requirements</span></span>  
 <span data-ttu-id="4eca6-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4eca6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eca6-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4eca6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4eca6-113">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4eca6-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4eca6-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eca6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eca6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4eca6-115">See Also</span></span>  
 [<span data-ttu-id="4eca6-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="4eca6-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="4eca6-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="4eca6-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
