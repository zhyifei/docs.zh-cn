---
title: IMetaDataImport::CountEnum 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
ms.openlocfilehash: 0c78ce8192d6456dd1b1be990d87b9209b028e09
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440369"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="4cb94-102">IMetaDataImport::CountEnum 方法</span><span class="sxs-lookup"><span data-stu-id="4cb94-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="4cb94-103">获取由指定枚举器检索的枚举中的元素数目。</span><span class="sxs-lookup"><span data-stu-id="4cb94-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb94-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cb94-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cb94-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cb94-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="4cb94-106">中枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="4cb94-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="4cb94-107">弄枚举的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="4cb94-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cb94-108">备注</span><span class="sxs-lookup"><span data-stu-id="4cb94-108">Remarks</span></span>  
 <span data-ttu-id="4cb94-109">`hEnum` 指定的句柄是从以前的 `Enum`*名称*调用（例如[IMetaDataImport：： EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)）获取的。</span><span class="sxs-lookup"><span data-stu-id="4cb94-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb94-110">要求</span><span class="sxs-lookup"><span data-stu-id="4cb94-110">Requirements</span></span>  
 <span data-ttu-id="4cb94-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cb94-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb94-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="4cb94-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4cb94-113">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="4cb94-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4cb94-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb94-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb94-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cb94-115">See also</span></span>

- [<span data-ttu-id="4cb94-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="4cb94-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4cb94-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="4cb94-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
