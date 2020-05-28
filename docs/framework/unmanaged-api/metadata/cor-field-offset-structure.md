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
ms.openlocfilehash: 70fb637cd1edf81be140b0e3306e3b0a483653a6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007983"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="2a4b1-102">COR_FIELD_OFFSET 结构</span><span class="sxs-lookup"><span data-stu-id="2a4b1-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="2a4b1-103">存储一个类中的指定字段的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2a4b1-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a4b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a4b1-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="2a4b1-105">成员</span><span class="sxs-lookup"><span data-stu-id="2a4b1-105">Members</span></span>  
  
|<span data-ttu-id="2a4b1-106">成员</span><span class="sxs-lookup"><span data-stu-id="2a4b1-106">Member</span></span>|<span data-ttu-id="2a4b1-107">描述</span><span class="sxs-lookup"><span data-stu-id="2a4b1-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="2a4b1-108">`mdFieldDef`表示字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="2a4b1-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="2a4b1-109">字段在其类中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2a4b1-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a4b1-110">备注</span><span class="sxs-lookup"><span data-stu-id="2a4b1-110">Remarks</span></span>  
 <span data-ttu-id="2a4b1-111">[IMetaDataImport：： GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md)和[IMetaDataEmit：： SetClassLayout](imetadataemit-setclasslayout-method.md)方法采用类型的参数 `COR_FIELD_OFFSET` 。</span><span class="sxs-lookup"><span data-stu-id="2a4b1-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a4b1-112">要求</span><span class="sxs-lookup"><span data-stu-id="2a4b1-112">Requirements</span></span>  
 <span data-ttu-id="2a4b1-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a4b1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a4b1-114">**标头：** Corhdr.h，Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="2a4b1-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="2a4b1-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a4b1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a4b1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a4b1-116">See also</span></span>

- [<span data-ttu-id="2a4b1-117">元数据结构</span><span class="sxs-lookup"><span data-stu-id="2a4b1-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="2a4b1-118">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="2a4b1-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2a4b1-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="2a4b1-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
