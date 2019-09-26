---
title: CLR_DEBUGGING_VERSION 结构
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4528ccd77fed2ea2a9b2d08243ffa1535bfad1ae
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274090"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="87f32-102">CLR_DEBUGGING_VERSION 结构</span><span class="sxs-lookup"><span data-stu-id="87f32-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="87f32-103">出于调试目的，定义公共语言运行时 (CLR) 的产品版本。</span><span class="sxs-lookup"><span data-stu-id="87f32-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f32-104">语法</span><span class="sxs-lookup"><span data-stu-id="87f32-104">Syntax</span></span>  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="87f32-105">成员</span><span class="sxs-lookup"><span data-stu-id="87f32-105">Members</span></span>  
  
|<span data-ttu-id="87f32-106">成员</span><span class="sxs-lookup"><span data-stu-id="87f32-106">Member</span></span>|<span data-ttu-id="87f32-107">描述</span><span class="sxs-lookup"><span data-stu-id="87f32-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="87f32-108">结构版本号</span><span class="sxs-lookup"><span data-stu-id="87f32-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="87f32-109">主版本号。</span><span class="sxs-lookup"><span data-stu-id="87f32-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="87f32-110">次版本号。</span><span class="sxs-lookup"><span data-stu-id="87f32-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="87f32-111">内部版本号。</span><span class="sxs-lookup"><span data-stu-id="87f32-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="87f32-112">修订号。</span><span class="sxs-lookup"><span data-stu-id="87f32-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87f32-113">备注</span><span class="sxs-lookup"><span data-stu-id="87f32-113">Remarks</span></span>  
 <span data-ttu-id="87f32-114">结构与 COR_VERSION 结构相同，但`CLR_DEBUGGING_VERSION`结构提供了附加的结构版本字段（`wStructVersion`）。 `CLR_DEBUGGING_VERSION`</span><span class="sxs-lookup"><span data-stu-id="87f32-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="87f32-115">此字段当前必须设置为零。</span><span class="sxs-lookup"><span data-stu-id="87f32-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87f32-116">要求</span><span class="sxs-lookup"><span data-stu-id="87f32-116">Requirements</span></span>  
 <span data-ttu-id="87f32-117">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87f32-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87f32-118">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="87f32-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="87f32-119">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87f32-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87f32-120">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87f32-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87f32-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="87f32-121">See also</span></span>

- [<span data-ttu-id="87f32-122">调试结构</span><span class="sxs-lookup"><span data-stu-id="87f32-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="87f32-123">调试</span><span class="sxs-lookup"><span data-stu-id="87f32-123">Debugging</span></span>](index.md)
