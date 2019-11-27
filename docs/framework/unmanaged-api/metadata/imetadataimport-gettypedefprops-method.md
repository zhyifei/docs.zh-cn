---
title: IMetaDataImport::GetTypeDefProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: c9ac624e17223def206e86fd92ee4fd2de7f6082
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436747"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="95355-102">IMetaDataImport::GetTypeDefProps 方法</span><span class="sxs-lookup"><span data-stu-id="95355-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="95355-103">返回指定的 TypeDef 标记所表示的 <xref:System.Type> 的元数据信息。</span><span class="sxs-lookup"><span data-stu-id="95355-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95355-104">语法</span><span class="sxs-lookup"><span data-stu-id="95355-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95355-105">参数</span><span class="sxs-lookup"><span data-stu-id="95355-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="95355-106">中TypeDef 标记，它表示要为其返回元数据的类型。</span><span class="sxs-lookup"><span data-stu-id="95355-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="95355-107">弄包含类型名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="95355-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="95355-108">中`szTypeDef`的大小（以宽字符为大小）。</span><span class="sxs-lookup"><span data-stu-id="95355-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="95355-109">弄`szTypeDef`中返回的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="95355-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="95355-110">弄指向修改类型定义的任何标志的指针。</span><span class="sxs-lookup"><span data-stu-id="95355-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="95355-111">此值是[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)枚举中的位掩码。</span><span class="sxs-lookup"><span data-stu-id="95355-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="95355-112">弄一个 TypeDef 或 TypeRef 元数据标记，它表示所请求类型的基类型。</span><span class="sxs-lookup"><span data-stu-id="95355-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95355-113">要求</span><span class="sxs-lookup"><span data-stu-id="95355-113">Requirements</span></span>  
 <span data-ttu-id="95355-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95355-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95355-115">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="95355-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95355-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="95355-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95355-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95355-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95355-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95355-118">See also</span></span>

- [<span data-ttu-id="95355-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="95355-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="95355-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="95355-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
