---
title: IMetaDataImport::FindTypeRef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeRef
helpviewer_keywords:
- IMetaDataImport::FindTypeRef method [.NET Framework metadata]
- FindTypeRef method [.NET Framework metadata]
ms.assetid: 1b2bbf3f-943e-412e-b66c-e802431b055c
topic_type:
- apiref
ms.openlocfilehash: 21a69d120cc732ca6659f77abc9f8ea0c993271e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437783"
---
# <a name="imetadataimportfindtyperef-method"></a><span data-ttu-id="3882f-102">IMetaDataImport::FindTypeRef 方法</span><span class="sxs-lookup"><span data-stu-id="3882f-102">IMetaDataImport::FindTypeRef Method</span></span>
<span data-ttu-id="3882f-103">获取一个指针，该指针指向指定范围内且具有指定名称的 <xref:System.Type> 引用的 TypeRef 标记。</span><span class="sxs-lookup"><span data-stu-id="3882f-103">Gets a pointer to the TypeRef token for the <xref:System.Type> reference that is in the specified scope and that has the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3882f-104">语法</span><span class="sxs-lookup"><span data-stu-id="3882f-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeRef (  
   [in] mdToken        tkResolutionScope,  
   [in]  LPCWSTR       szName,  
   [out] mdTypeRef     *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3882f-105">参数</span><span class="sxs-lookup"><span data-stu-id="3882f-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="3882f-106">中一个 ModuleRef、AssemblyRef 或 TypeRef 标记，分别指定定义了类型引用的模块、程序集或类型。</span><span class="sxs-lookup"><span data-stu-id="3882f-106">[in] A ModuleRef, AssemblyRef, or TypeRef token that specifies the module, assembly, or type, respectively, in which the type reference is defined.</span></span>  
  
 `szName`  
 <span data-ttu-id="3882f-107">中要搜索的类型引用的名称。</span><span class="sxs-lookup"><span data-stu-id="3882f-107">[in] The name of the type reference to search for.</span></span>  
  
 `ptr`  
 <span data-ttu-id="3882f-108">弄指向匹配的 TypeRef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="3882f-108">[out] A pointer to the matching TypeRef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3882f-109">要求</span><span class="sxs-lookup"><span data-stu-id="3882f-109">Requirements</span></span>  
 <span data-ttu-id="3882f-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3882f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3882f-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="3882f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3882f-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3882f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3882f-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3882f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3882f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3882f-114">See also</span></span>

- [<span data-ttu-id="3882f-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3882f-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3882f-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="3882f-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
