---
title: IMetaDataImport::GetClassLayout 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: e02d7dd4b287d027b633ae9bf2e98e036062bdd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175403"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="d7e94-102">IMetaDataImport::GetClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="d7e94-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="d7e94-103">获取指定的 TypeDef 标记所引用类的布局信息。</span><span class="sxs-lookup"><span data-stu-id="d7e94-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e94-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7e94-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7e94-105">parameters</span><span class="sxs-lookup"><span data-stu-id="d7e94-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d7e94-106">[在]要返回布局的类的 TypeDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="d7e94-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="d7e94-107">[出]值 1、2、4、8 或 16，表示类的包大小。</span><span class="sxs-lookup"><span data-stu-id="d7e94-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="d7e94-108">[出][COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)值的数组。</span><span class="sxs-lookup"><span data-stu-id="d7e94-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d7e94-109">[in] `rFieldOffset` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="d7e94-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="d7e94-110">[出]中`rFieldOffset`返回的元素数。</span><span class="sxs-lookup"><span data-stu-id="d7e94-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="d7e94-111">[出]以 的类大小（以字节为单位）。 `td`</span><span class="sxs-lookup"><span data-stu-id="d7e94-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7e94-112">要求</span><span class="sxs-lookup"><span data-stu-id="d7e94-112">Requirements</span></span>  
 <span data-ttu-id="d7e94-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7e94-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7e94-114">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="d7e94-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7e94-115">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="d7e94-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7e94-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7e94-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e94-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7e94-117">See also</span></span>

- [<span data-ttu-id="d7e94-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d7e94-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d7e94-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d7e94-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
