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
ms.openlocfilehash: 0ed1579886f1682348a136be3391f6bdc2543d26
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007385"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="d687f-102">CorFileMapping 枚举</span><span class="sxs-lookup"><span data-stu-id="d687f-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="d687f-103">包含一些值，这些值描述从对[IMetaDataInfo：： GetFileMapping](imetadatainfo-getfilemapping-method.md)方法的调用返回的文件映射的类型。</span><span class="sxs-lookup"><span data-stu-id="d687f-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d687f-104">语法</span><span class="sxs-lookup"><span data-stu-id="d687f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="d687f-105">成员</span><span class="sxs-lookup"><span data-stu-id="d687f-105">Members</span></span>  
  
|<span data-ttu-id="d687f-106">成员</span><span class="sxs-lookup"><span data-stu-id="d687f-106">Member</span></span>|<span data-ttu-id="d687f-107">描述</span><span class="sxs-lookup"><span data-stu-id="d687f-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="d687f-108">文件映射为数据文件。</span><span class="sxs-lookup"><span data-stu-id="d687f-108">The file is mapped as a data file.</span></span> <span data-ttu-id="d687f-109">也就是说， `SEC_IMAGE` 标志未传递到 Microsoft Win32 `CreateFileMapping` 函数。</span><span class="sxs-lookup"><span data-stu-id="d687f-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="d687f-110">使用 `LoadLibrary` 函数或带有标志的函数为执行映射文件 `CreateFileMapping` `SEC_IMAGE` 。</span><span class="sxs-lookup"><span data-stu-id="d687f-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d687f-111">要求</span><span class="sxs-lookup"><span data-stu-id="d687f-111">Requirements</span></span>  
 <span data-ttu-id="d687f-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d687f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d687f-113">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="d687f-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d687f-114">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d687f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d687f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d687f-115">See also</span></span>

- [<span data-ttu-id="d687f-116">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="d687f-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="d687f-117">GetFileMapping 方法</span><span class="sxs-lookup"><span data-stu-id="d687f-117">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)
