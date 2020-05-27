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
ms.openlocfilehash: 1307f555c9d8b6d28febcf25db89ae856c143d71
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009400"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="0e95c-102">AssemblyRefFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="0e95c-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="0e95c-103">包含用于描述程序集引用的功能的值。</span><span class="sxs-lookup"><span data-stu-id="0e95c-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e95c-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e95c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0e95c-105">成员</span><span class="sxs-lookup"><span data-stu-id="0e95c-105">Members</span></span>  
  
|<span data-ttu-id="0e95c-106">成员</span><span class="sxs-lookup"><span data-stu-id="0e95c-106">Member</span></span>|<span data-ttu-id="0e95c-107">描述</span><span class="sxs-lookup"><span data-stu-id="0e95c-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="0e95c-108">指定程序集引用包含有关程序集的发布服务器的完整的未哈哈希信息。</span><span class="sxs-lookup"><span data-stu-id="0e95c-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e95c-109">要求</span><span class="sxs-lookup"><span data-stu-id="0e95c-109">Requirements</span></span>  
 <span data-ttu-id="0e95c-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e95c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e95c-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="0e95c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e95c-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e95c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e95c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e95c-113">See also</span></span>

- [<span data-ttu-id="0e95c-114">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="0e95c-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="0e95c-115">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="0e95c-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="0e95c-116">DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="0e95c-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
