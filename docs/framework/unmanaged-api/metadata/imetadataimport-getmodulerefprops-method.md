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
ms.openlocfilehash: dce9b9c20cbc73c6a70a34afa6c348c23164ed9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437321"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="3742c-102">IMetaDataImport::GetModuleRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="3742c-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="3742c-103">获取指定元数据标记引用的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="3742c-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3742c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3742c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3742c-105">参数</span><span class="sxs-lookup"><span data-stu-id="3742c-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="3742c-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span><span class="sxs-lookup"><span data-stu-id="3742c-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="3742c-107">[out] A buffer to hold the module name.</span><span class="sxs-lookup"><span data-stu-id="3742c-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3742c-108">[in] The requested size of `szName` in wide characters.</span><span class="sxs-lookup"><span data-stu-id="3742c-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="3742c-109">[out] The returned size of `szName` in wide characters.</span><span class="sxs-lookup"><span data-stu-id="3742c-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3742c-110">要求</span><span class="sxs-lookup"><span data-stu-id="3742c-110">Requirements</span></span>  
 <span data-ttu-id="3742c-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3742c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3742c-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3742c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3742c-113">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3742c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3742c-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3742c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3742c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3742c-115">See also</span></span>

- [<span data-ttu-id="3742c-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3742c-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3742c-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3742c-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
