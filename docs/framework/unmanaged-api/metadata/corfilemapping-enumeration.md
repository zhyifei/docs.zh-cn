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
ms.openlocfilehash: 3c8864aa604b0483130eac5aa0d7c0640abbac99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443718"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="604c5-102">CorFileMapping 枚举</span><span class="sxs-lookup"><span data-stu-id="604c5-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="604c5-103">包含值，用于描述从调用返回的文件映射的类型[imetadatainfo::](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="604c5-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="604c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="604c5-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="604c5-105">成员</span><span class="sxs-lookup"><span data-stu-id="604c5-105">Members</span></span>  
  
|<span data-ttu-id="604c5-106">成员</span><span class="sxs-lookup"><span data-stu-id="604c5-106">Member</span></span>|<span data-ttu-id="604c5-107">描述</span><span class="sxs-lookup"><span data-stu-id="604c5-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="604c5-108">作为数据文件映射文件。</span><span class="sxs-lookup"><span data-stu-id="604c5-108">The file is mapped as a data file.</span></span> <span data-ttu-id="604c5-109">也就是说，`SEC_IMAGE`标志中未传递给 Microsoft Win32`CreateFileMapping`函数。</span><span class="sxs-lookup"><span data-stu-id="604c5-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="604c5-110">该文件为映射，则执行、 通过使用`LoadLibrary`函数或`CreateFileMapping`起作用`SEC_IMAGE`标志。</span><span class="sxs-lookup"><span data-stu-id="604c5-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="604c5-111">要求</span><span class="sxs-lookup"><span data-stu-id="604c5-111">Requirements</span></span>  
 <span data-ttu-id="604c5-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="604c5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="604c5-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="604c5-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="604c5-114">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="604c5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604c5-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="604c5-115">See Also</span></span>  
 [<span data-ttu-id="604c5-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="604c5-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="604c5-117">GetFileMapping 方法</span><span class="sxs-lookup"><span data-stu-id="604c5-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
