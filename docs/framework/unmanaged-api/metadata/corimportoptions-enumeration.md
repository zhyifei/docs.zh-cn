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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156125"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="045e8-102">CorImportOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="045e8-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="045e8-103">包含一些标志值，用于在导入当前作用域范围外的程序集的过程中控制行为。</span><span class="sxs-lookup"><span data-stu-id="045e8-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="045e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="045e8-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="045e8-105">成员</span><span class="sxs-lookup"><span data-stu-id="045e8-105">Members</span></span>  
  
|<span data-ttu-id="045e8-106">成员</span><span class="sxs-lookup"><span data-stu-id="045e8-106">Member</span></span>|<span data-ttu-id="045e8-107">描述</span><span class="sxs-lookup"><span data-stu-id="045e8-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="045e8-108">指示默认行为，就是要跳过已删除的记录。</span><span class="sxs-lookup"><span data-stu-id="045e8-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="045e8-109">指示应该列举所有元数据。</span><span class="sxs-lookup"><span data-stu-id="045e8-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="045e8-110">指示应该列举所有的 Typedef，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="045e8-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="045e8-111">指示应该列举所有 MethodDefs，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="045e8-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="045e8-112">指示应该列举所有 FieldDefs，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="045e8-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="045e8-113">指示应该列举所有 PropertyDefs，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="045e8-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="045e8-114">指示应该列举所有 EventDefs，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="045e8-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="045e8-115">指示应该列举所有自定义属性，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="045e8-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="045e8-116">指示应该列举所有导出的类型，包括已删除的。</span><span class="sxs-lookup"><span data-stu-id="045e8-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="045e8-117">要求</span><span class="sxs-lookup"><span data-stu-id="045e8-117">Requirements</span></span>  
 <span data-ttu-id="045e8-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="045e8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="045e8-119">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="045e8-119">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="045e8-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="045e8-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="045e8-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="045e8-121">See also</span></span>

- [<span data-ttu-id="045e8-122">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="045e8-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
