---
title: CorLinkerOptions 枚举
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d154985e9c1614e6b8f13a55410ead0cb5e861b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441050"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="3b829-102">CorLinkerOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="3b829-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="3b829-103">指定用于选择元数据链接器的选项的标志。</span><span class="sxs-lookup"><span data-stu-id="3b829-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b829-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b829-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="3b829-105">成员</span><span class="sxs-lookup"><span data-stu-id="3b829-105">Members</span></span>  
  
|<span data-ttu-id="3b829-106">成员</span><span class="sxs-lookup"><span data-stu-id="3b829-106">Member</span></span>|<span data-ttu-id="3b829-107">描述</span><span class="sxs-lookup"><span data-stu-id="3b829-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="3b829-108">不会保留的专用类型和全局函数。</span><span class="sxs-lookup"><span data-stu-id="3b829-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="3b829-109">保留的专用类型和全局函数。</span><span class="sxs-lookup"><span data-stu-id="3b829-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b829-110">要求</span><span class="sxs-lookup"><span data-stu-id="3b829-110">Requirements</span></span>  
 <span data-ttu-id="3b829-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b829-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b829-112">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3b829-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3b829-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b829-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b829-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b829-114">See Also</span></span>  
 [<span data-ttu-id="3b829-115">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="3b829-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
