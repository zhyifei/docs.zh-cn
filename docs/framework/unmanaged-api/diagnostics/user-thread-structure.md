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
ms.openlocfilehash: 51db7a2b6464b562e09ce061991898a8d604ead1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437967"
---
# <a name="user_thread-structure"></a><span data-ttu-id="6cf14-102">USER_THREAD 结构</span><span class="sxs-lookup"><span data-stu-id="6cf14-102">USER_THREAD Structure</span></span>
<span data-ttu-id="6cf14-103">向调试器提供有关线程的信息。</span><span class="sxs-lookup"><span data-stu-id="6cf14-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="6cf14-104">有关详细信息，请参阅[INotifySource2：： SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6cf14-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cf14-105">语法</span><span class="sxs-lookup"><span data-stu-id="6cf14-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="6cf14-106">Members</span><span class="sxs-lookup"><span data-stu-id="6cf14-106">Members</span></span>  
  
|<span data-ttu-id="6cf14-107">成员</span><span class="sxs-lookup"><span data-stu-id="6cf14-107">Member</span></span>|<span data-ttu-id="6cf14-108">说明</span><span class="sxs-lookup"><span data-stu-id="6cf14-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="6cf14-109">线程缓冲区的地址。</span><span class="sxs-lookup"><span data-stu-id="6cf14-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="6cf14-110">线程缓冲区的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6cf14-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="6cf14-111">线程 ID。</span><span class="sxs-lookup"><span data-stu-id="6cf14-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6cf14-112">要求</span><span class="sxs-lookup"><span data-stu-id="6cf14-112">Requirements</span></span>  
 <span data-ttu-id="6cf14-113">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="6cf14-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf14-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cf14-114">See also</span></span>

- [<span data-ttu-id="6cf14-115">SetNotifyFilter 方法</span><span class="sxs-lookup"><span data-stu-id="6cf14-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="6cf14-116">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="6cf14-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
