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
ms.openlocfilehash: de120516655c1a0578e88ecc2890701ed9fc2f6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="e37af-102">AssemblyRefFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="e37af-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="e37af-103">包含值，用于描述程序集引用的功能。</span><span class="sxs-lookup"><span data-stu-id="e37af-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e37af-104">语法</span><span class="sxs-lookup"><span data-stu-id="e37af-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e37af-105">成员</span><span class="sxs-lookup"><span data-stu-id="e37af-105">Members</span></span>  
  
|<span data-ttu-id="e37af-106">成员</span><span class="sxs-lookup"><span data-stu-id="e37af-106">Member</span></span>|<span data-ttu-id="e37af-107">描述</span><span class="sxs-lookup"><span data-stu-id="e37af-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="e37af-108">指定程序集引用包含完整的未经哈希的发布服务器信息的程序集。</span><span class="sxs-lookup"><span data-stu-id="e37af-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e37af-109">要求</span><span class="sxs-lookup"><span data-stu-id="e37af-109">Requirements</span></span>  
 <span data-ttu-id="e37af-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e37af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e37af-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e37af-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e37af-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e37af-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e37af-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e37af-113">See Also</span></span>  
 [<span data-ttu-id="e37af-114">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="e37af-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="e37af-115">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="e37af-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="e37af-116">DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="e37af-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
