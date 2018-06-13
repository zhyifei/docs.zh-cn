---
title: CorPEKind 枚举
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5869eb16bd768d58a6f27a83f2d8d51914a8aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443110"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="f7fd1-102">CorPEKind 枚举</span><span class="sxs-lookup"><span data-stu-id="f7fd1-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="f7fd1-103">包含值，用于描述一个可移植可执行 (PE) 文件，从调用返回[imetadataimport2:: Getpekind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)。</span><span class="sxs-lookup"><span data-stu-id="f7fd1-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7fd1-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7fd1-104">Syntax</span></span>  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="f7fd1-105">成员</span><span class="sxs-lookup"><span data-stu-id="f7fd1-105">Members</span></span>  
  
|<span data-ttu-id="f7fd1-106">成员</span><span class="sxs-lookup"><span data-stu-id="f7fd1-106">Member</span></span>|<span data-ttu-id="f7fd1-107">描述</span><span class="sxs-lookup"><span data-stu-id="f7fd1-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="f7fd1-108">指示这不是 PE 文件。</span><span class="sxs-lookup"><span data-stu-id="f7fd1-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="f7fd1-109">指示此 PE 文件包含仅托管代码。</span><span class="sxs-lookup"><span data-stu-id="f7fd1-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="f7fd1-110">指示此 PE 文件执行 Win32 调用。</span><span class="sxs-lookup"><span data-stu-id="f7fd1-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="f7fd1-111">指示此 PE 文件，在 64 位平台上运行。</span><span class="sxs-lookup"><span data-stu-id="f7fd1-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="f7fd1-112">指示此 PE 文件是本机代码。</span><span class="sxs-lookup"><span data-stu-id="f7fd1-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="f7fd1-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="f7fd1-113">pe32BitPreferred</span></span>|<span data-ttu-id="f7fd1-114">指示此 PE 文件是以非特定于平台的以及更希望要加载在 32 位环境中。</span><span class="sxs-lookup"><span data-stu-id="f7fd1-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7fd1-115">备注</span><span class="sxs-lookup"><span data-stu-id="f7fd1-115">Remarks</span></span>  
 <span data-ttu-id="f7fd1-116">按位组合，可以使用这些值。</span><span class="sxs-lookup"><span data-stu-id="f7fd1-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7fd1-117">要求</span><span class="sxs-lookup"><span data-stu-id="f7fd1-117">Requirements</span></span>  
 <span data-ttu-id="f7fd1-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7fd1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7fd1-119">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f7fd1-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f7fd1-120">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7fd1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7fd1-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7fd1-121">See Also</span></span>  
 [<span data-ttu-id="f7fd1-122">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="f7fd1-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
