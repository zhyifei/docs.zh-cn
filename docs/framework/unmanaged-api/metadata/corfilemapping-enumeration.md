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
ms.openlocfilehash: e9b3802c9c72ec3a9302e403e55789aab8102cf1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624985"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="9cd39-102">CorFileMapping 枚举</span><span class="sxs-lookup"><span data-stu-id="9cd39-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="9cd39-103">包含描述从调用返回的文件映射的类型的值[imetadatainfo:: Getfilemapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9cd39-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cd39-104">语法</span><span class="sxs-lookup"><span data-stu-id="9cd39-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="9cd39-105">成员</span><span class="sxs-lookup"><span data-stu-id="9cd39-105">Members</span></span>  
  
|<span data-ttu-id="9cd39-106">成员</span><span class="sxs-lookup"><span data-stu-id="9cd39-106">Member</span></span>|<span data-ttu-id="9cd39-107">描述</span><span class="sxs-lookup"><span data-stu-id="9cd39-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="9cd39-108">为数据文件映射文件。</span><span class="sxs-lookup"><span data-stu-id="9cd39-108">The file is mapped as a data file.</span></span> <span data-ttu-id="9cd39-109">即`SEC_IMAGE`标志未传递到 Microsoft Win32`CreateFileMapping`函数。</span><span class="sxs-lookup"><span data-stu-id="9cd39-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="9cd39-110">对于执行，通过使用映射文件`LoadLibrary`函数或`CreateFileMapping`函数与`SEC_IMAGE`标志。</span><span class="sxs-lookup"><span data-stu-id="9cd39-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9cd39-111">要求</span><span class="sxs-lookup"><span data-stu-id="9cd39-111">Requirements</span></span>  
 <span data-ttu-id="9cd39-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9cd39-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cd39-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9cd39-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9cd39-114">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cd39-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cd39-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cd39-115">See also</span></span>
- [<span data-ttu-id="9cd39-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="9cd39-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="9cd39-117">GetFileMapping 方法</span><span class="sxs-lookup"><span data-stu-id="9cd39-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
