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
ms.openlocfilehash: 5144feab742bc5dac36563d701d81a699d0bb2f3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609438"
---
# <a name="user_thread-structure"></a><span data-ttu-id="6158e-102">USER_THREAD 结构</span><span class="sxs-lookup"><span data-stu-id="6158e-102">USER_THREAD Structure</span></span>
<span data-ttu-id="6158e-103">向调试器提供有关线程的信息。</span><span class="sxs-lookup"><span data-stu-id="6158e-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="6158e-104">有关详细信息，请参阅[INotifySource2：： SetNotifyFilter](inotifysource2-setnotifyfilter-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6158e-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6158e-105">语法</span><span class="sxs-lookup"><span data-stu-id="6158e-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="6158e-106">成员</span><span class="sxs-lookup"><span data-stu-id="6158e-106">Members</span></span>  
  
|<span data-ttu-id="6158e-107">成员</span><span class="sxs-lookup"><span data-stu-id="6158e-107">Member</span></span>|<span data-ttu-id="6158e-108">描述</span><span class="sxs-lookup"><span data-stu-id="6158e-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="6158e-109">线程缓冲区的地址。</span><span class="sxs-lookup"><span data-stu-id="6158e-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="6158e-110">线程缓冲区的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6158e-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="6158e-111">线程 ID。</span><span class="sxs-lookup"><span data-stu-id="6158e-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6158e-112">要求</span><span class="sxs-lookup"><span data-stu-id="6158e-112">Requirements</span></span>  
 <span data-ttu-id="6158e-113">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="6158e-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6158e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6158e-114">See also</span></span>

- [<span data-ttu-id="6158e-115">SetNotifyFilter 方法</span><span class="sxs-lookup"><span data-stu-id="6158e-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="6158e-116">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="6158e-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
