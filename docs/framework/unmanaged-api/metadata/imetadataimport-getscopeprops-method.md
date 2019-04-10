---
title: IMetaDataImport::GetScopeProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 17568a46c8e946989af0e401366d7eaa885886da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220963"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="e89b0-102">IMetaDataImport::GetScopeProps 方法</span><span class="sxs-lookup"><span data-stu-id="e89b0-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="e89b0-103">获取当前元数据范围内的程序集或模块的名称和版本标识符（可选）。</span><span class="sxs-lookup"><span data-stu-id="e89b0-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e89b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="e89b0-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e89b0-105">参数</span><span class="sxs-lookup"><span data-stu-id="e89b0-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e89b0-106">[out]程序集或模块名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e89b0-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e89b0-107">[in]在宽字符为单位的大小`szName`。</span><span class="sxs-lookup"><span data-stu-id="e89b0-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="e89b0-108">[out]在中返回的宽字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="e89b0-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="e89b0-109">[out，optional]指向唯一地标识程序集或模块的版本的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="e89b0-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e89b0-110">备注</span><span class="sxs-lookup"><span data-stu-id="e89b0-110">Remarks</span></span>  
 <span data-ttu-id="e89b0-111">[Imetadataemit:: Setmoduleprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)方法用于设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="e89b0-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e89b0-112">要求</span><span class="sxs-lookup"><span data-stu-id="e89b0-112">Requirements</span></span>  
 <span data-ttu-id="e89b0-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e89b0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e89b0-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e89b0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e89b0-115">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e89b0-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e89b0-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="e89b0-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e89b0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e89b0-117">See also</span></span>

- [<span data-ttu-id="e89b0-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="e89b0-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e89b0-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="e89b0-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
