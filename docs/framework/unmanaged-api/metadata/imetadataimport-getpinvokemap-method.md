---
title: IMetaDataImport::GetPinvokeMap 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99aea385cf5e3c8bcf7cf39b7cc5618f99f8a631
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121701"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="f647f-102">IMetaDataImport::GetPinvokeMap 方法</span><span class="sxs-lookup"><span data-stu-id="f647f-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="f647f-103">获取用于表示 PInvoke 调用的目标程序集的 ModuleRef 标记。</span><span class="sxs-lookup"><span data-stu-id="f647f-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f647f-104">语法</span><span class="sxs-lookup"><span data-stu-id="f647f-104">Syntax</span></span>  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f647f-105">参数</span><span class="sxs-lookup"><span data-stu-id="f647f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f647f-106">[in]要获取的 PInvoke 映射元数据的新对象或 FieldDef 标记。</span><span class="sxs-lookup"><span data-stu-id="f647f-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="f647f-107">[out]一个指向用于映射的标志。</span><span class="sxs-lookup"><span data-stu-id="f647f-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="f647f-108">此值是从一个位掩码[CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="f647f-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="f647f-109">[out]非托管目标 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="f647f-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="f647f-110">[in]在宽字符为单位的大小`szImportName`。</span><span class="sxs-lookup"><span data-stu-id="f647f-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="f647f-111">[out]在中返回的宽字符数`szImportName`。</span><span class="sxs-lookup"><span data-stu-id="f647f-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="f647f-112">[out]指向表示非托管的目标对象库的 ModuleRef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="f647f-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f647f-113">要求</span><span class="sxs-lookup"><span data-stu-id="f647f-113">Requirements</span></span>  
 <span data-ttu-id="f647f-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f647f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f647f-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f647f-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f647f-116">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f647f-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f647f-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f647f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f647f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f647f-118">See also</span></span>

- [<span data-ttu-id="f647f-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f647f-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f647f-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="f647f-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
