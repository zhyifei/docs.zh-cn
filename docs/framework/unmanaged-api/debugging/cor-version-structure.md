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
ms.openlocfilehash: cc9a67e16635209c3bf303e97dc3e5938943a653
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099090"
---
# <a name="cor_version-structure"></a><span data-ttu-id="b2ad7-102">COR_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="b2ad7-102">COR_VERSION Structure</span></span>
<span data-ttu-id="b2ad7-103">存储由四个部分组成的公共语言运行时标准版本号。</span><span class="sxs-lookup"><span data-stu-id="b2ad7-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2ad7-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2ad7-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="b2ad7-105">Members</span><span class="sxs-lookup"><span data-stu-id="b2ad7-105">Members</span></span>  
  
|<span data-ttu-id="b2ad7-106">成员</span><span class="sxs-lookup"><span data-stu-id="b2ad7-106">Member</span></span>|<span data-ttu-id="b2ad7-107">描述</span><span class="sxs-lookup"><span data-stu-id="b2ad7-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="b2ad7-108">主版本号。</span><span class="sxs-lookup"><span data-stu-id="b2ad7-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="b2ad7-109">次版本号。</span><span class="sxs-lookup"><span data-stu-id="b2ad7-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="b2ad7-110">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="b2ad7-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="b2ad7-111">子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="b2ad7-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2ad7-112">备注</span><span class="sxs-lookup"><span data-stu-id="b2ad7-112">Remarks</span></span>  
 <span data-ttu-id="b2ad7-113">如果版本号为1.0.3705.288，1为主要版本号，0为次版本号，3705为内部版本号，288为子内部版本号。</span><span class="sxs-lookup"><span data-stu-id="b2ad7-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2ad7-114">要求</span><span class="sxs-lookup"><span data-stu-id="b2ad7-114">Requirements</span></span>  
 <span data-ttu-id="b2ad7-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2ad7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2ad7-116">**标头：** Cordebug.idl .idl</span><span class="sxs-lookup"><span data-stu-id="b2ad7-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="b2ad7-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2ad7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2ad7-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2ad7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ad7-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2ad7-119">See also</span></span>

- [<span data-ttu-id="b2ad7-120">调试结构</span><span class="sxs-lookup"><span data-stu-id="b2ad7-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b2ad7-121">调试</span><span class="sxs-lookup"><span data-stu-id="b2ad7-121">Debugging</span></span>](index.md)
