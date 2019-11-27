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
ms.openlocfilehash: 23d293a87112c62cb2127b435faeca258a7de226
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444226"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="f23c2-102">AssemblyRefFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="f23c2-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="f23c2-103">包含用于描述程序集引用的功能的值。</span><span class="sxs-lookup"><span data-stu-id="f23c2-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f23c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="f23c2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f23c2-105">Members</span><span class="sxs-lookup"><span data-stu-id="f23c2-105">Members</span></span>  
  
|<span data-ttu-id="f23c2-106">成员</span><span class="sxs-lookup"><span data-stu-id="f23c2-106">Member</span></span>|<span data-ttu-id="f23c2-107">说明</span><span class="sxs-lookup"><span data-stu-id="f23c2-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="f23c2-108">指定程序集引用包含有关程序集的发布服务器的完整的未哈哈希信息。</span><span class="sxs-lookup"><span data-stu-id="f23c2-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f23c2-109">要求</span><span class="sxs-lookup"><span data-stu-id="f23c2-109">Requirements</span></span>  
 <span data-ttu-id="f23c2-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f23c2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f23c2-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f23c2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f23c2-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f23c2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23c2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f23c2-113">See also</span></span>

- [<span data-ttu-id="f23c2-114">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="f23c2-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="f23c2-115">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="f23c2-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="f23c2-116">DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="f23c2-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
