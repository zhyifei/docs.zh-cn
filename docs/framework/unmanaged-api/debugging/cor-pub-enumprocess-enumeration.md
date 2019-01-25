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
ms.openlocfilehash: bfc576e1b4f0bf1666dcd585a24dbfa398e9abde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715850"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="ea5e7-102">COR_PUB_ENUMPROCESS 枚举</span><span class="sxs-lookup"><span data-stu-id="ea5e7-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="ea5e7-103">标识要枚举的进程的类型。</span><span class="sxs-lookup"><span data-stu-id="ea5e7-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea5e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea5e7-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="ea5e7-105">成员</span><span class="sxs-lookup"><span data-stu-id="ea5e7-105">Members</span></span>  
  
|<span data-ttu-id="ea5e7-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="ea5e7-106">Member name</span></span>|<span data-ttu-id="ea5e7-107">描述</span><span class="sxs-lookup"><span data-stu-id="ea5e7-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="ea5e7-108">托管的进程。</span><span class="sxs-lookup"><span data-stu-id="ea5e7-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea5e7-109">备注</span><span class="sxs-lookup"><span data-stu-id="ea5e7-109">Remarks</span></span>  
 <span data-ttu-id="ea5e7-110">非托管调试 API 的当前版本仅枚举托管进程。</span><span class="sxs-lookup"><span data-stu-id="ea5e7-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea5e7-111">要求</span><span class="sxs-lookup"><span data-stu-id="ea5e7-111">Requirements</span></span>  
 <span data-ttu-id="ea5e7-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea5e7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea5e7-113">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ea5e7-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ea5e7-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea5e7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea5e7-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea5e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea5e7-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea5e7-116">See also</span></span>
- [<span data-ttu-id="ea5e7-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="ea5e7-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
