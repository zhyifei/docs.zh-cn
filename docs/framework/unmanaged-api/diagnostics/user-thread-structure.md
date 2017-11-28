---
title: "USER_THREAD 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: USER_THREAD
api_location: diasymreader.dll
api_type: COM
f1_keywords: USER_THREAD
helpviewer_keywords: USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d93002fe5460bfdb36d4e11c74410677b46a98d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="userthread-structure"></a><span data-ttu-id="fd113-102">USER_THREAD 结构</span><span class="sxs-lookup"><span data-stu-id="fd113-102">USER_THREAD Structure</span></span>
<span data-ttu-id="fd113-103">提供对有关线程调试器的信息。</span><span class="sxs-lookup"><span data-stu-id="fd113-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="fd113-104">有关详细信息，请参阅[inotifysource2:: Setnotifyfilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fd113-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd113-105">语法</span><span class="sxs-lookup"><span data-stu-id="fd113-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="fd113-106">成员</span><span class="sxs-lookup"><span data-stu-id="fd113-106">Members</span></span>  
  
|<span data-ttu-id="fd113-107">成员</span><span class="sxs-lookup"><span data-stu-id="fd113-107">Member</span></span>|<span data-ttu-id="fd113-108">描述</span><span class="sxs-lookup"><span data-stu-id="fd113-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="fd113-109">线程缓冲区的地址。</span><span class="sxs-lookup"><span data-stu-id="fd113-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="fd113-110">线程缓冲区，以字节为单位的长度。</span><span class="sxs-lookup"><span data-stu-id="fd113-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="fd113-111">线程 id。</span><span class="sxs-lookup"><span data-stu-id="fd113-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd113-112">要求</span><span class="sxs-lookup"><span data-stu-id="fd113-112">Requirements</span></span>  
 <span data-ttu-id="fd113-113">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="fd113-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd113-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd113-114">See Also</span></span>  
 [<span data-ttu-id="fd113-115">SetNotifyFilter 方法</span><span class="sxs-lookup"><span data-stu-id="fd113-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)  
 [<span data-ttu-id="fd113-116">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="fd113-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
