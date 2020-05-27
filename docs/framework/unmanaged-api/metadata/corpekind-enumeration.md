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
ms.openlocfilehash: 8b6eab8156f72847eb6dd3369950f9b46a3fc877
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007554"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="ade91-102">CorPEKind 枚举</span><span class="sxs-lookup"><span data-stu-id="ade91-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="ade91-103">包含描述可移植可执行（PE）文件的值，这些值是从对[IMetaDataImport2：： GetPEKind](imetadataimport2-getpekind-method.md)的调用返回的。</span><span class="sxs-lookup"><span data-stu-id="ade91-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ade91-104">语法</span><span class="sxs-lookup"><span data-stu-id="ade91-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="ade91-105">成员</span><span class="sxs-lookup"><span data-stu-id="ade91-105">Members</span></span>  
  
|<span data-ttu-id="ade91-106">成员</span><span class="sxs-lookup"><span data-stu-id="ade91-106">Member</span></span>|<span data-ttu-id="ade91-107">描述</span><span class="sxs-lookup"><span data-stu-id="ade91-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="ade91-108">指示这不是 PE 文件。</span><span class="sxs-lookup"><span data-stu-id="ade91-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="ade91-109">指示此 PE 文件仅包含托管代码。</span><span class="sxs-lookup"><span data-stu-id="ade91-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="ade91-110">指示此 PE 文件进行 Win32 调用。</span><span class="sxs-lookup"><span data-stu-id="ade91-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="ade91-111">指示此 PE 文件在64位平台上运行。</span><span class="sxs-lookup"><span data-stu-id="ade91-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="ade91-112">指示此 PE 文件是本机代码。</span><span class="sxs-lookup"><span data-stu-id="ade91-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="ade91-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="ade91-113">pe32BitPreferred</span></span>|<span data-ttu-id="ade91-114">指示此 PE 文件与平台无关，并倾向于在32位环境中加载。</span><span class="sxs-lookup"><span data-stu-id="ade91-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ade91-115">备注</span><span class="sxs-lookup"><span data-stu-id="ade91-115">Remarks</span></span>  
 <span data-ttu-id="ade91-116">这些值可用于按位组合。</span><span class="sxs-lookup"><span data-stu-id="ade91-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ade91-117">要求</span><span class="sxs-lookup"><span data-stu-id="ade91-117">Requirements</span></span>  
 <span data-ttu-id="ade91-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ade91-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ade91-119">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="ade91-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ade91-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ade91-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade91-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ade91-121">See also</span></span>

- [<span data-ttu-id="ade91-122">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="ade91-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
