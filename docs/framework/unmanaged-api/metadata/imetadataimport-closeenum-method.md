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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f27955467436d562c6a9acc9d7f666427e4c85b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770712"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="32e3a-102">IMetaDataImport::CloseEnum 方法</span><span class="sxs-lookup"><span data-stu-id="32e3a-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="32e3a-103">关闭由指定句柄的枚举器。</span><span class="sxs-lookup"><span data-stu-id="32e3a-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e3a-104">语法</span><span class="sxs-lookup"><span data-stu-id="32e3a-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32e3a-105">参数</span><span class="sxs-lookup"><span data-stu-id="32e3a-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="32e3a-106">[in]枚举器来关闭句柄。</span><span class="sxs-lookup"><span data-stu-id="32e3a-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32e3a-107">备注</span><span class="sxs-lookup"><span data-stu-id="32e3a-107">Remarks</span></span>  
 <span data-ttu-id="32e3a-108">通过指定的句柄`hEnum`获取从以前`Enum`*名称*调用 (例如， [imetadataimport:: Enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md))。</span><span class="sxs-lookup"><span data-stu-id="32e3a-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e3a-109">要求</span><span class="sxs-lookup"><span data-stu-id="32e3a-109">Requirements</span></span>  
 <span data-ttu-id="32e3a-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="32e3a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e3a-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="32e3a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32e3a-112">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="32e3a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32e3a-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32e3a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e3a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="32e3a-114">See also</span></span>

- [<span data-ttu-id="32e3a-115">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="32e3a-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="32e3a-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="32e3a-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
