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
ms.openlocfilehash: 0191f1fa17d436944fcb590d88dd4004adfa1aba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744298"
---
# <a name="userthread-structure"></a><span data-ttu-id="3faeb-102">USER_THREAD 结构</span><span class="sxs-lookup"><span data-stu-id="3faeb-102">USER_THREAD Structure</span></span>
<span data-ttu-id="3faeb-103">提供给关于线程调试程序的信息。</span><span class="sxs-lookup"><span data-stu-id="3faeb-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="3faeb-104">有关详细信息，请参阅[INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3faeb-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3faeb-105">语法</span><span class="sxs-lookup"><span data-stu-id="3faeb-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="3faeb-106">成员</span><span class="sxs-lookup"><span data-stu-id="3faeb-106">Members</span></span>  
  
|<span data-ttu-id="3faeb-107">成员</span><span class="sxs-lookup"><span data-stu-id="3faeb-107">Member</span></span>|<span data-ttu-id="3faeb-108">描述</span><span class="sxs-lookup"><span data-stu-id="3faeb-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="3faeb-109">线程缓冲区的地址。</span><span class="sxs-lookup"><span data-stu-id="3faeb-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="3faeb-110">线程缓冲区，以字节为单位的长度。</span><span class="sxs-lookup"><span data-stu-id="3faeb-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="3faeb-111">线程 id。</span><span class="sxs-lookup"><span data-stu-id="3faeb-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3faeb-112">要求</span><span class="sxs-lookup"><span data-stu-id="3faeb-112">Requirements</span></span>  
 <span data-ttu-id="3faeb-113">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="3faeb-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3faeb-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3faeb-114">See also</span></span>

- [<span data-ttu-id="3faeb-115">SetNotifyFilter 方法</span><span class="sxs-lookup"><span data-stu-id="3faeb-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="3faeb-116">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="3faeb-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
