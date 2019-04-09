---
title: COR_FIELD_OFFSET 结构
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 820c99de1bdb108a24203a3438b1709ca54490b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078117"
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="cc7b6-102">COR_FIELD_OFFSET 结构</span><span class="sxs-lookup"><span data-stu-id="cc7b6-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="cc7b6-103">存储一个类中的指定字段的偏移量。</span><span class="sxs-lookup"><span data-stu-id="cc7b6-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc7b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc7b6-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="cc7b6-105">成员</span><span class="sxs-lookup"><span data-stu-id="cc7b6-105">Members</span></span>  
  
|<span data-ttu-id="cc7b6-106">成员</span><span class="sxs-lookup"><span data-stu-id="cc7b6-106">Member</span></span>|<span data-ttu-id="cc7b6-107">描述</span><span class="sxs-lookup"><span data-stu-id="cc7b6-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="cc7b6-108">`mdFieldDef`元数据标记所表示的字段。</span><span class="sxs-lookup"><span data-stu-id="cc7b6-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="cc7b6-109">在它的类，该字段的偏移量。</span><span class="sxs-lookup"><span data-stu-id="cc7b6-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc7b6-110">备注</span><span class="sxs-lookup"><span data-stu-id="cc7b6-110">Remarks</span></span>  
 <span data-ttu-id="cc7b6-111">[Imetadataimport:: Getclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md)并[imetadataemit:: Setclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)方法接受类型参数的`COR_FIELD_OFFSET`。</span><span class="sxs-lookup"><span data-stu-id="cc7b6-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc7b6-112">要求</span><span class="sxs-lookup"><span data-stu-id="cc7b6-112">Requirements</span></span>  
 <span data-ttu-id="cc7b6-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc7b6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc7b6-114">**标头：** CorHdr.h CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="cc7b6-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 **<span data-ttu-id="cc7b6-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="cc7b6-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cc7b6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc7b6-116">See also</span></span>

- [<span data-ttu-id="cc7b6-117">元数据结构</span><span class="sxs-lookup"><span data-stu-id="cc7b6-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="cc7b6-118">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="cc7b6-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cc7b6-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="cc7b6-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
