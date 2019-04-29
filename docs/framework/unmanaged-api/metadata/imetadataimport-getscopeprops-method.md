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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777547"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="0a4b4-102">IMetaDataImport::GetScopeProps 方法</span><span class="sxs-lookup"><span data-stu-id="0a4b4-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="0a4b4-103">获取当前元数据范围内的程序集或模块的名称和版本标识符（可选）。</span><span class="sxs-lookup"><span data-stu-id="0a4b4-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a4b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a4b4-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a4b4-105">参数</span><span class="sxs-lookup"><span data-stu-id="0a4b4-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0a4b4-106">[out]程序集或模块名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0a4b4-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0a4b4-107">[in]在宽字符为单位的大小`szName`。</span><span class="sxs-lookup"><span data-stu-id="0a4b4-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="0a4b4-108">[out]在中返回的宽字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="0a4b4-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="0a4b4-109">[out，optional]指向唯一地标识程序集或模块的版本的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="0a4b4-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a4b4-110">备注</span><span class="sxs-lookup"><span data-stu-id="0a4b4-110">Remarks</span></span>  
 <span data-ttu-id="0a4b4-111">[Imetadataemit:: Setmoduleprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)方法用于设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="0a4b4-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a4b4-112">要求</span><span class="sxs-lookup"><span data-stu-id="0a4b4-112">Requirements</span></span>  
 <span data-ttu-id="0a4b4-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4b4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a4b4-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a4b4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a4b4-115">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0a4b4-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a4b4-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a4b4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4b4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a4b4-117">See also</span></span>

- [<span data-ttu-id="0a4b4-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="0a4b4-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0a4b4-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="0a4b4-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
