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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 076d5de3e9d1925e3a030fee4a06a89862105897
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045859"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="b8d16-102">CorFileFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="b8d16-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="b8d16-103">包含值，用于描述对的调用中定义的文件类型[imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b8d16-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8d16-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8d16-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b8d16-105">成员</span><span class="sxs-lookup"><span data-stu-id="b8d16-105">Members</span></span>  
  
|<span data-ttu-id="b8d16-106">成员</span><span class="sxs-lookup"><span data-stu-id="b8d16-106">Member</span></span>|<span data-ttu-id="b8d16-107">描述</span><span class="sxs-lookup"><span data-stu-id="b8d16-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="b8d16-108">指示该文件不是一个资源文件。</span><span class="sxs-lookup"><span data-stu-id="b8d16-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="b8d16-109">指示该文件，可能是资源文件不包含元数据。</span><span class="sxs-lookup"><span data-stu-id="b8d16-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8d16-110">要求</span><span class="sxs-lookup"><span data-stu-id="b8d16-110">Requirements</span></span>  
 <span data-ttu-id="b8d16-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8d16-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8d16-112">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b8d16-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b8d16-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8d16-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d16-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8d16-114">See also</span></span>

- [<span data-ttu-id="b8d16-115">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="b8d16-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
