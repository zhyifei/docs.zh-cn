---
title: "CoreClrDebugProcInfo 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugProcInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 53616fb8e947d2a301dcfcb4e3870a9a9dc36ec1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="e2add-102">CoreClrDebugProcInfo 结构</span><span class="sxs-lookup"><span data-stu-id="e2add-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="e2add-103">表示在远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="e2add-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2add-104">语法</span><span class="sxs-lookup"><span data-stu-id="e2add-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="e2add-105">成员</span><span class="sxs-lookup"><span data-stu-id="e2add-105">Members</span></span>  
  
|<span data-ttu-id="e2add-106">成员</span><span class="sxs-lookup"><span data-stu-id="e2add-106">Member</span></span>|<span data-ttu-id="e2add-107">描述</span><span class="sxs-lookup"><span data-stu-id="e2add-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="e2add-108">操作系统分配的进程标识符。</span><span class="sxs-lookup"><span data-stu-id="e2add-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="e2add-109">由运行在目标计算机上的远程调试代理分配的进程标识符。</span><span class="sxs-lookup"><span data-stu-id="e2add-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="e2add-110">此标识符的回收通常少于 OS 标识符。</span><span class="sxs-lookup"><span data-stu-id="e2add-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="e2add-111">进程的命令行。</span><span class="sxs-lookup"><span data-stu-id="e2add-111">Command-line of the process.</span></span> <span data-ttu-id="e2add-112">此成员可能会被截断。</span><span class="sxs-lookup"><span data-stu-id="e2add-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2add-113">要求</span><span class="sxs-lookup"><span data-stu-id="e2add-113">Requirements</span></span>  
 <span data-ttu-id="e2add-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2add-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2add-115">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="e2add-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="e2add-116">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="e2add-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="e2add-117">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e2add-117">**.NET Framework Versions:** 3.5 SP1</span></span>
