---
title: USER_THREAD 结构
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: acc4da79796e975d349d1cb33c301c25c4791cb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709073"
---
# <a name="userthread-structure"></a><span data-ttu-id="0da8d-102">USER_THREAD 结构</span><span class="sxs-lookup"><span data-stu-id="0da8d-102">USER_THREAD Structure</span></span>
<span data-ttu-id="0da8d-103">提供给关于线程调试程序的信息。</span><span class="sxs-lookup"><span data-stu-id="0da8d-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="0da8d-104">有关详细信息，请参阅[INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0da8d-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da8d-105">语法</span><span class="sxs-lookup"><span data-stu-id="0da8d-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="0da8d-106">成员</span><span class="sxs-lookup"><span data-stu-id="0da8d-106">Members</span></span>  
  
|<span data-ttu-id="0da8d-107">成员</span><span class="sxs-lookup"><span data-stu-id="0da8d-107">Member</span></span>|<span data-ttu-id="0da8d-108">描述</span><span class="sxs-lookup"><span data-stu-id="0da8d-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="0da8d-109">线程缓冲区的地址。</span><span class="sxs-lookup"><span data-stu-id="0da8d-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="0da8d-110">线程缓冲区，以字节为单位的长度。</span><span class="sxs-lookup"><span data-stu-id="0da8d-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="0da8d-111">线程 id。</span><span class="sxs-lookup"><span data-stu-id="0da8d-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0da8d-112">要求</span><span class="sxs-lookup"><span data-stu-id="0da8d-112">Requirements</span></span>  
 <span data-ttu-id="0da8d-113">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="0da8d-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da8d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0da8d-114">See also</span></span>
- [<span data-ttu-id="0da8d-115">SetNotifyFilter 方法</span><span class="sxs-lookup"><span data-stu-id="0da8d-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="0da8d-116">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="0da8d-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
