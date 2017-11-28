---
title: "CorFileFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorFileFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorFileFlags
helpviewer_keywords: CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf123f734f73ecfe726a80099de6ec06b0ced06b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="79c4d-102">CorFileFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="79c4d-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="79c4d-103">包含值，用于描述对的调用中定义的文件类型[imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="79c4d-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79c4d-104">语法</span><span class="sxs-lookup"><span data-stu-id="79c4d-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="79c4d-105">成员</span><span class="sxs-lookup"><span data-stu-id="79c4d-105">Members</span></span>  
  
|<span data-ttu-id="79c4d-106">成员</span><span class="sxs-lookup"><span data-stu-id="79c4d-106">Member</span></span>|<span data-ttu-id="79c4d-107">描述</span><span class="sxs-lookup"><span data-stu-id="79c4d-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="79c4d-108">指示该文件不是资源文件。</span><span class="sxs-lookup"><span data-stu-id="79c4d-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="79c4d-109">指示该文件，可能是资源文件，不包含元数据。</span><span class="sxs-lookup"><span data-stu-id="79c4d-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79c4d-110">要求</span><span class="sxs-lookup"><span data-stu-id="79c4d-110">Requirements</span></span>  
 <span data-ttu-id="79c4d-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="79c4d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79c4d-112">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="79c4d-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="79c4d-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79c4d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c4d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79c4d-114">See Also</span></span>  
 [<span data-ttu-id="79c4d-115">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="79c4d-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
