---
title: CorImportOptions 枚举
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2f71a277484adbbfe3628222c635528cdab03e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59156125"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="da17e-102">CorImportOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="da17e-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="da17e-103">包含一些标志值，用于在导入当前作用域范围外的程序集的过程中控制行为。</span><span class="sxs-lookup"><span data-stu-id="da17e-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da17e-104">语法</span><span class="sxs-lookup"><span data-stu-id="da17e-104">Syntax</span></span>  
  
```  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="da17e-105">成员</span><span class="sxs-lookup"><span data-stu-id="da17e-105">Members</span></span>  
  
|<span data-ttu-id="da17e-106">成员</span><span class="sxs-lookup"><span data-stu-id="da17e-106">Member</span></span>|<span data-ttu-id="da17e-107">描述</span><span class="sxs-lookup"><span data-stu-id="da17e-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="da17e-108">指示默认行为，就是要跳过已删除的记录。</span><span class="sxs-lookup"><span data-stu-id="da17e-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="da17e-109">指示应该列举所有元数据。</span><span class="sxs-lookup"><span data-stu-id="da17e-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="da17e-110">指示应该列举所有的 Typedef，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="da17e-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="da17e-111">指示应该列举所有 MethodDefs，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="da17e-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="da17e-112">指示应该列举所有 FieldDefs，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="da17e-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="da17e-113">指示应该列举所有 PropertyDefs，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="da17e-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="da17e-114">指示应该列举所有 EventDefs，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="da17e-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="da17e-115">指示应该列举所有自定义属性，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="da17e-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="da17e-116">指示应该列举所有导出的类型，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="da17e-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da17e-117">要求</span><span class="sxs-lookup"><span data-stu-id="da17e-117">Requirements</span></span>  
 <span data-ttu-id="da17e-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="da17e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da17e-119">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="da17e-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="da17e-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da17e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da17e-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="da17e-121">See also</span></span>

- [<span data-ttu-id="da17e-122">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="da17e-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
