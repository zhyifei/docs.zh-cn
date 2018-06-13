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
ms.openlocfilehash: 7ecc2f62a6bb8119b7fe06a82aea827a58d04ecb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441663"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="6fdcf-102">CorFileFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="6fdcf-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="6fdcf-103">包含值，用于描述对的调用中定义的文件类型[imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="6fdcf-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fdcf-104">语法</span><span class="sxs-lookup"><span data-stu-id="6fdcf-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6fdcf-105">成员</span><span class="sxs-lookup"><span data-stu-id="6fdcf-105">Members</span></span>  
  
|<span data-ttu-id="6fdcf-106">成员</span><span class="sxs-lookup"><span data-stu-id="6fdcf-106">Member</span></span>|<span data-ttu-id="6fdcf-107">描述</span><span class="sxs-lookup"><span data-stu-id="6fdcf-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="6fdcf-108">指示该文件不是资源文件。</span><span class="sxs-lookup"><span data-stu-id="6fdcf-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="6fdcf-109">指示该文件，可能是资源文件，不包含元数据。</span><span class="sxs-lookup"><span data-stu-id="6fdcf-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fdcf-110">要求</span><span class="sxs-lookup"><span data-stu-id="6fdcf-110">Requirements</span></span>  
 <span data-ttu-id="6fdcf-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6fdcf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fdcf-112">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6fdcf-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6fdcf-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fdcf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fdcf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fdcf-114">See Also</span></span>  
 [<span data-ttu-id="6fdcf-115">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="6fdcf-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
