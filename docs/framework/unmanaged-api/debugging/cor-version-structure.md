---
title: COR_VERSION 结构
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffbe571ebc3d14c12e57b1f805d77e56e97d12e1
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274171"
---
# <a name="cor_version-structure"></a><span data-ttu-id="19828-102">COR_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="19828-102">COR_VERSION Structure</span></span>
<span data-ttu-id="19828-103">存储由四个部分组成的公共语言运行时标准版本号。</span><span class="sxs-lookup"><span data-stu-id="19828-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19828-104">语法</span><span class="sxs-lookup"><span data-stu-id="19828-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="19828-105">成员</span><span class="sxs-lookup"><span data-stu-id="19828-105">Members</span></span>  
  
|<span data-ttu-id="19828-106">成员</span><span class="sxs-lookup"><span data-stu-id="19828-106">Member</span></span>|<span data-ttu-id="19828-107">描述</span><span class="sxs-lookup"><span data-stu-id="19828-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="19828-108">主版本号。</span><span class="sxs-lookup"><span data-stu-id="19828-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="19828-109">次版本号。</span><span class="sxs-lookup"><span data-stu-id="19828-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="19828-110">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="19828-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="19828-111">子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="19828-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19828-112">备注</span><span class="sxs-lookup"><span data-stu-id="19828-112">Remarks</span></span>  
 <span data-ttu-id="19828-113">如果版本号为1.0.3705.288，1为主要版本号，0为次版本号，3705为内部版本号，288为子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="19828-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19828-114">要求</span><span class="sxs-lookup"><span data-stu-id="19828-114">Requirements</span></span>  
 <span data-ttu-id="19828-115">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19828-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19828-116">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="19828-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="19828-117">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19828-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19828-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19828-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19828-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="19828-119">See also</span></span>

- [<span data-ttu-id="19828-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="19828-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="19828-121">调试</span><span class="sxs-lookup"><span data-stu-id="19828-121">Debugging</span></span>](index.md)
