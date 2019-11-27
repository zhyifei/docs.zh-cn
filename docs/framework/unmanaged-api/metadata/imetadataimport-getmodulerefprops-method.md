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
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="3e4be-102">IMetaDataImport::GetModuleRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="3e4be-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="3e4be-103">获取指定元数据标记引用的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="3e4be-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e4be-104">语法</span><span class="sxs-lookup"><span data-stu-id="3e4be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e4be-105">参数</span><span class="sxs-lookup"><span data-stu-id="3e4be-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="3e4be-106">中引用要获取其元数据信息的模块的 ModuleRef 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="3e4be-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="3e4be-107">弄用于保存模块名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3e4be-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3e4be-108">中请求的 `szName` 大小（宽字符）。</span><span class="sxs-lookup"><span data-stu-id="3e4be-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="3e4be-109">弄以宽字符返回 `szName` 的大小。</span><span class="sxs-lookup"><span data-stu-id="3e4be-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e4be-110">要求</span><span class="sxs-lookup"><span data-stu-id="3e4be-110">Requirements</span></span>  
 <span data-ttu-id="3e4be-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e4be-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e4be-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="3e4be-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e4be-113">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3e4be-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e4be-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e4be-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e4be-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e4be-115">See also</span></span>

- [<span data-ttu-id="3e4be-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3e4be-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3e4be-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3e4be-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
