---
title: "AssemblyRefFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyRefFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyRefFlags
helpviewer_keywords: AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a749a2f0016e7f2ea22c1d61c82f25ac78a9b9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="0c493-102">AssemblyRefFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="0c493-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="0c493-103">包含值，用于描述程序集引用的功能。</span><span class="sxs-lookup"><span data-stu-id="0c493-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c493-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c493-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0c493-105">成员</span><span class="sxs-lookup"><span data-stu-id="0c493-105">Members</span></span>  
  
|<span data-ttu-id="0c493-106">成员</span><span class="sxs-lookup"><span data-stu-id="0c493-106">Member</span></span>|<span data-ttu-id="0c493-107">描述</span><span class="sxs-lookup"><span data-stu-id="0c493-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="0c493-108">指定程序集引用包含完整的未经哈希的发布服务器信息的程序集。</span><span class="sxs-lookup"><span data-stu-id="0c493-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c493-109">惠?</span><span class="sxs-lookup"><span data-stu-id="0c493-109">Requirements</span></span>  
 <span data-ttu-id="0c493-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c493-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c493-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c493-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c493-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c493-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c493-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c493-113">See Also</span></span>  
 [<span data-ttu-id="0c493-114">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="0c493-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="0c493-115">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="0c493-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="0c493-116">DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="0c493-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
