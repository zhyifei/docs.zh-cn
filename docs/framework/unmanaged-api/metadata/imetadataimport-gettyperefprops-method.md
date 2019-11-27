---
title: IMetaDataImport::GetTypeRefProps 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 6ea7605e062eb77e0488b3a9561c4d83be16fa7d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436711"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="1991c-102">IMetaDataImport::GetTypeRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="1991c-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="1991c-103">获取与指定的 TypeRef 标记所引用的 <xref:System.Type> 关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="1991c-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1991c-104">语法</span><span class="sxs-lookup"><span data-stu-id="1991c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1991c-105">参数</span><span class="sxs-lookup"><span data-stu-id="1991c-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="1991c-106">中TypeRef 标记，它表示要为其返回元数据的类型。</span><span class="sxs-lookup"><span data-stu-id="1991c-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="1991c-107">弄指向在其中进行引用的范围的指针。</span><span class="sxs-lookup"><span data-stu-id="1991c-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="1991c-108">此值为 AssemblyRef 或 ModuleRef 标记。</span><span class="sxs-lookup"><span data-stu-id="1991c-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="1991c-109">弄包含类型名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1991c-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="1991c-110">中`szName`中的请求大小（以宽字符为大小）。</span><span class="sxs-lookup"><span data-stu-id="1991c-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="1991c-111">弄`szName`的宽字符返回的大小。</span><span class="sxs-lookup"><span data-stu-id="1991c-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1991c-112">要求</span><span class="sxs-lookup"><span data-stu-id="1991c-112">Requirements</span></span>  
 <span data-ttu-id="1991c-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1991c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1991c-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="1991c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1991c-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1991c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1991c-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1991c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1991c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1991c-117">See also</span></span>

- [<span data-ttu-id="1991c-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="1991c-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1991c-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="1991c-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
