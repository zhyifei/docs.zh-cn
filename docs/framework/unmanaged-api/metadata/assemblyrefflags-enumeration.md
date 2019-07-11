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
ms.openlocfilehash: c402dcda79f013b19b091c6309b3d71951018a18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776366"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="dd7f3-102">AssemblyRefFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="dd7f3-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="dd7f3-103">包含值，用于描述程序集引用的功能。</span><span class="sxs-lookup"><span data-stu-id="dd7f3-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd7f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd7f3-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="dd7f3-105">成员</span><span class="sxs-lookup"><span data-stu-id="dd7f3-105">Members</span></span>  
  
|<span data-ttu-id="dd7f3-106">成员</span><span class="sxs-lookup"><span data-stu-id="dd7f3-106">Member</span></span>|<span data-ttu-id="dd7f3-107">描述</span><span class="sxs-lookup"><span data-stu-id="dd7f3-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="dd7f3-108">指定程序集引用包含完整的、 未经哈希的发布服务器信息的程序集。</span><span class="sxs-lookup"><span data-stu-id="dd7f3-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd7f3-109">要求</span><span class="sxs-lookup"><span data-stu-id="dd7f3-109">Requirements</span></span>  
 <span data-ttu-id="dd7f3-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd7f3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd7f3-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd7f3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd7f3-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd7f3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd7f3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd7f3-113">See also</span></span>

- [<span data-ttu-id="dd7f3-114">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="dd7f3-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="dd7f3-115">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="dd7f3-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="dd7f3-116">DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="dd7f3-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
