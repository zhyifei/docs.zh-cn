---
title: CorFileFlags 枚举
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
ms.openlocfilehash: c315e2ae2753b59b4e277764d27c3fb3388b515c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445417"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="c9734-102">CorFileFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="c9734-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="c9734-103">包含一些值，这些值描述在对[IMetaDataAssemblyEmit：:D efinefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)的调用中定义的文件类型。</span><span class="sxs-lookup"><span data-stu-id="c9734-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9734-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9734-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c9734-105">Members</span><span class="sxs-lookup"><span data-stu-id="c9734-105">Members</span></span>  
  
|<span data-ttu-id="c9734-106">成员</span><span class="sxs-lookup"><span data-stu-id="c9734-106">Member</span></span>|<span data-ttu-id="c9734-107">说明</span><span class="sxs-lookup"><span data-stu-id="c9734-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="c9734-108">指示该文件不是资源文件。</span><span class="sxs-lookup"><span data-stu-id="c9734-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="c9734-109">指示文件可能不包含元数据，可能是资源文件。</span><span class="sxs-lookup"><span data-stu-id="c9734-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9734-110">要求</span><span class="sxs-lookup"><span data-stu-id="c9734-110">Requirements</span></span>  
 <span data-ttu-id="c9734-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9734-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9734-112">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="c9734-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c9734-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9734-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9734-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9734-114">See also</span></span>

- [<span data-ttu-id="c9734-115">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="c9734-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
