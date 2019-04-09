---
title: COR_PUB_ENUMPROCESS 枚举
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02ff60852a85d003deb68cae96a184ac8d61c65f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089401"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="940b1-102">COR_PUB_ENUMPROCESS 枚举</span><span class="sxs-lookup"><span data-stu-id="940b1-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="940b1-103">标识要枚举的进程的类型。</span><span class="sxs-lookup"><span data-stu-id="940b1-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="940b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="940b1-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="940b1-105">成员</span><span class="sxs-lookup"><span data-stu-id="940b1-105">Members</span></span>  
  
|<span data-ttu-id="940b1-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="940b1-106">Member name</span></span>|<span data-ttu-id="940b1-107">描述</span><span class="sxs-lookup"><span data-stu-id="940b1-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="940b1-108">托管的进程。</span><span class="sxs-lookup"><span data-stu-id="940b1-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="940b1-109">备注</span><span class="sxs-lookup"><span data-stu-id="940b1-109">Remarks</span></span>  
 <span data-ttu-id="940b1-110">非托管调试 API 的当前版本仅枚举托管进程。</span><span class="sxs-lookup"><span data-stu-id="940b1-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="940b1-111">要求</span><span class="sxs-lookup"><span data-stu-id="940b1-111">Requirements</span></span>  
 <span data-ttu-id="940b1-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="940b1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="940b1-113">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="940b1-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="940b1-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="940b1-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="940b1-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="940b1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="940b1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="940b1-116">See also</span></span>

- [<span data-ttu-id="940b1-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="940b1-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
