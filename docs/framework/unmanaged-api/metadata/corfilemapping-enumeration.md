---
title: CorFileMapping 枚举
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3056836d289383161f9fa538c3c6349f88b6ba6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175612"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="85b4f-102">CorFileMapping 枚举</span><span class="sxs-lookup"><span data-stu-id="85b4f-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="85b4f-103">包含描述从调用返回的文件映射的类型的值[imetadatainfo:: Getfilemapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="85b4f-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85b4f-104">语法</span><span class="sxs-lookup"><span data-stu-id="85b4f-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="85b4f-105">成员</span><span class="sxs-lookup"><span data-stu-id="85b4f-105">Members</span></span>  
  
|<span data-ttu-id="85b4f-106">成员</span><span class="sxs-lookup"><span data-stu-id="85b4f-106">Member</span></span>|<span data-ttu-id="85b4f-107">描述</span><span class="sxs-lookup"><span data-stu-id="85b4f-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="85b4f-108">为数据文件映射文件。</span><span class="sxs-lookup"><span data-stu-id="85b4f-108">The file is mapped as a data file.</span></span> <span data-ttu-id="85b4f-109">即`SEC_IMAGE`标志未传递到 Microsoft Win32`CreateFileMapping`函数。</span><span class="sxs-lookup"><span data-stu-id="85b4f-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="85b4f-110">对于执行，通过使用映射文件`LoadLibrary`函数或`CreateFileMapping`函数与`SEC_IMAGE`标志。</span><span class="sxs-lookup"><span data-stu-id="85b4f-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85b4f-111">要求</span><span class="sxs-lookup"><span data-stu-id="85b4f-111">Requirements</span></span>  
 <span data-ttu-id="85b4f-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85b4f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85b4f-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="85b4f-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="85b4f-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="85b4f-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="85b4f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="85b4f-115">See also</span></span>

- [<span data-ttu-id="85b4f-116">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="85b4f-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="85b4f-117">GetFileMapping 方法</span><span class="sxs-lookup"><span data-stu-id="85b4f-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
