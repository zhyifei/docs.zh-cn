---
title: IMetaDataImport::GetModuleRefProps 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e948644e4f2d91b2f1e3e3627f7adbe204dee9d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155410"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="eac65-102">IMetaDataImport::GetModuleRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="eac65-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="eac65-103">获取指定元数据标记引用的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="eac65-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eac65-104">语法</span><span class="sxs-lookup"><span data-stu-id="eac65-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eac65-105">参数</span><span class="sxs-lookup"><span data-stu-id="eac65-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="eac65-106">[in]ModuleRef 元数据标记所引用的模块，若要获取的元数据信息。</span><span class="sxs-lookup"><span data-stu-id="eac65-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="eac65-107">[out]用于保存模块名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="eac65-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="eac65-108">[in]请求的大小`szName`以宽字符为单位。</span><span class="sxs-lookup"><span data-stu-id="eac65-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="eac65-109">[out]在返回的大小的`szName`以宽字符为单位。</span><span class="sxs-lookup"><span data-stu-id="eac65-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eac65-110">要求</span><span class="sxs-lookup"><span data-stu-id="eac65-110">Requirements</span></span>  
 <span data-ttu-id="eac65-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eac65-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eac65-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eac65-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eac65-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eac65-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eac65-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eac65-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac65-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="eac65-115">See also</span></span>

- [<span data-ttu-id="eac65-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="eac65-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eac65-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="eac65-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
