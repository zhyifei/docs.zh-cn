---
title: IMetaDataImport::CloseEnum 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
ms.openlocfilehash: 4347a4da3e58a20c98e217de3a71c448e244eb29
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440116"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="84892-102">IMetaDataImport::CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="84892-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="84892-103">关闭由指定句柄标识的枚举器。</span><span class="sxs-lookup"><span data-stu-id="84892-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84892-104">语法</span><span class="sxs-lookup"><span data-stu-id="84892-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84892-105">参数</span><span class="sxs-lookup"><span data-stu-id="84892-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="84892-106">中要关闭的枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="84892-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84892-107">备注</span><span class="sxs-lookup"><span data-stu-id="84892-107">Remarks</span></span>  
 <span data-ttu-id="84892-108">`hEnum` 指定的句柄是从以前的 `Enum`*名称*调用（例如[IMetaDataImport：： EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)）获取的。</span><span class="sxs-lookup"><span data-stu-id="84892-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84892-109">要求</span><span class="sxs-lookup"><span data-stu-id="84892-109">Requirements</span></span>  
 <span data-ttu-id="84892-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84892-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84892-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="84892-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84892-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="84892-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="84892-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84892-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84892-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84892-114">See also</span></span>

- [<span data-ttu-id="84892-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="84892-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="84892-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="84892-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
