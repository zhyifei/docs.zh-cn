---
title: "CoreClrDebugRuntimeInfo 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugRuntimeInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e18416822aed6020fb0de8eb5bc7d38e4cd2eb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="47892-102">CoreClrDebugRuntimeInfo 结构</span><span class="sxs-lookup"><span data-stu-id="47892-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="47892-103">表示公共语言运行时 (CLR) 实例，该实例加载到远程计算机上的进程中。</span><span class="sxs-lookup"><span data-stu-id="47892-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47892-104">语法</span><span class="sxs-lookup"><span data-stu-id="47892-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="47892-105">成员</span><span class="sxs-lookup"><span data-stu-id="47892-105">Members</span></span>  
  
|<span data-ttu-id="47892-106">成员</span><span class="sxs-lookup"><span data-stu-id="47892-106">Member</span></span>|<span data-ttu-id="47892-107">描述</span><span class="sxs-lookup"><span data-stu-id="47892-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="47892-108">由运行在目标计算机上的远程调试代理分配的运行时标识符。</span><span class="sxs-lookup"><span data-stu-id="47892-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47892-109">要求</span><span class="sxs-lookup"><span data-stu-id="47892-109">Requirements</span></span>  
 <span data-ttu-id="47892-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47892-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47892-111">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="47892-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="47892-112">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="47892-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="47892-113">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="47892-113">**.NET Framework Versions:** 3.5 SP1</span></span>
