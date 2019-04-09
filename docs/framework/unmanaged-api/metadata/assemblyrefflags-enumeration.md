---
title: AssemblyRefFlags 枚举
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc98b2421d23ffd6dfb716a8cc782b46a9d59ce0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128890"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="18a76-102">AssemblyRefFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="18a76-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="18a76-103">包含值，用于描述程序集引用的功能。</span><span class="sxs-lookup"><span data-stu-id="18a76-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a76-104">语法</span><span class="sxs-lookup"><span data-stu-id="18a76-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="18a76-105">成员</span><span class="sxs-lookup"><span data-stu-id="18a76-105">Members</span></span>  
  
|<span data-ttu-id="18a76-106">成员</span><span class="sxs-lookup"><span data-stu-id="18a76-106">Member</span></span>|<span data-ttu-id="18a76-107">描述</span><span class="sxs-lookup"><span data-stu-id="18a76-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="18a76-108">指定程序集引用包含完整的、 未经哈希的发布服务器信息的程序集。</span><span class="sxs-lookup"><span data-stu-id="18a76-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18a76-109">要求</span><span class="sxs-lookup"><span data-stu-id="18a76-109">Requirements</span></span>  
 <span data-ttu-id="18a76-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18a76-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18a76-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="18a76-111">**Header:** Cor.h</span></span>  
  
 **<span data-ttu-id="18a76-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="18a76-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18a76-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="18a76-113">See also</span></span>

- [<span data-ttu-id="18a76-114">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="18a76-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="18a76-115">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="18a76-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="18a76-116">DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="18a76-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
