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
ms.openlocfilehash: d8f830ca7e273b65dc9ec77566a02df6c32cd464
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202386"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="ea785-102">CorPEKind 枚举</span><span class="sxs-lookup"><span data-stu-id="ea785-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="ea785-103">包含值，用于描述一个可移植可执行 (PE) 文件，如从调用返回[IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ea785-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea785-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea785-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ea785-105">成员</span><span class="sxs-lookup"><span data-stu-id="ea785-105">Members</span></span>  
  
|<span data-ttu-id="ea785-106">成员</span><span class="sxs-lookup"><span data-stu-id="ea785-106">Member</span></span>|<span data-ttu-id="ea785-107">描述</span><span class="sxs-lookup"><span data-stu-id="ea785-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="ea785-108">指示这不是 PE 文件。</span><span class="sxs-lookup"><span data-stu-id="ea785-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="ea785-109">指示此 PE 文件包含仅托管代码。</span><span class="sxs-lookup"><span data-stu-id="ea785-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="ea785-110">指示此 PE 文件进行 Win32 调用。</span><span class="sxs-lookup"><span data-stu-id="ea785-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="ea785-111">指示此 PE 文件在 64 位平台上运行。</span><span class="sxs-lookup"><span data-stu-id="ea785-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="ea785-112">指示此 PE 文件是本机代码。</span><span class="sxs-lookup"><span data-stu-id="ea785-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="ea785-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="ea785-113">pe32BitPreferred</span></span>|<span data-ttu-id="ea785-114">指示此 PE 文件与平台无关，并且更适合于创建要在 32 位环境中加载。</span><span class="sxs-lookup"><span data-stu-id="ea785-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea785-115">备注</span><span class="sxs-lookup"><span data-stu-id="ea785-115">Remarks</span></span>  
 <span data-ttu-id="ea785-116">按位组合中，可以使用这些值。</span><span class="sxs-lookup"><span data-stu-id="ea785-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea785-117">要求</span><span class="sxs-lookup"><span data-stu-id="ea785-117">Requirements</span></span>  
 <span data-ttu-id="ea785-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea785-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea785-119">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ea785-119">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="ea785-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="ea785-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea785-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea785-121">See also</span></span>

- [<span data-ttu-id="ea785-122">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="ea785-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
