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
ms.openlocfilehash: f46033b9e643ef6b4a0063c4995b8c024b8c1f7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175351"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="ac3fe-102">IMetaDataImport::GetModuleRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="ac3fe-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="ac3fe-103">获取指定元数据标记引用的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="ac3fe-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac3fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac3fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac3fe-105">parameters</span><span class="sxs-lookup"><span data-stu-id="ac3fe-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="ac3fe-106">[在]ModuleRef 元数据令牌，用于引用模块以获取元数据信息。</span><span class="sxs-lookup"><span data-stu-id="ac3fe-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="ac3fe-107">[出]保存模块名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ac3fe-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ac3fe-108">[在]以宽字符表示`szName`请求的大小。</span><span class="sxs-lookup"><span data-stu-id="ac3fe-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ac3fe-109">[出]以宽字符返回`szName`的大小。</span><span class="sxs-lookup"><span data-stu-id="ac3fe-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac3fe-110">要求</span><span class="sxs-lookup"><span data-stu-id="ac3fe-110">Requirements</span></span>  
 <span data-ttu-id="ac3fe-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac3fe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac3fe-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="ac3fe-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac3fe-113">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="ac3fe-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac3fe-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac3fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac3fe-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac3fe-115">See also</span></span>

- [<span data-ttu-id="ac3fe-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="ac3fe-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ac3fe-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="ac3fe-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
