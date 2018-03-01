---
title: "IDebugAutoAttach::AutoAttach 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b875fec2fdb6ecaeaccf8e58030b2fccbb8653b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="19321-102">IDebugAutoAttach::AutoAttach 方法</span><span class="sxs-lookup"><span data-stu-id="19321-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="19321-103">执行服务器调用调试器自动附加。</span><span class="sxs-lookup"><span data-stu-id="19321-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19321-104">语法</span><span class="sxs-lookup"><span data-stu-id="19321-104">Syntax</span></span>  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19321-105">参数</span><span class="sxs-lookup"><span data-stu-id="19321-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="19321-106">[in]始终设置为`GUID_NULL`。</span><span class="sxs-lookup"><span data-stu-id="19321-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="19321-107">[in]进程 ID，通常使用检索`GetCurrentProcessId`函数。</span><span class="sxs-lookup"><span data-stu-id="19321-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="19321-108">[in]程序类型： `AUTOATTACH_PROGRAM_WIN32`， `AUTOATTACH_PROGRAM_COMPLUS`，或`AUTOATTACH_PROGRAM_UNKNOWN`。</span><span class="sxs-lookup"><span data-stu-id="19321-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="19321-109">[in]程序 id。</span><span class="sxs-lookup"><span data-stu-id="19321-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="19321-110">[in]通过 debug 谓词传递的字符串。</span><span class="sxs-lookup"><span data-stu-id="19321-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19321-111">返回值</span><span class="sxs-lookup"><span data-stu-id="19321-111">Return Value</span></span>  
 <span data-ttu-id="19321-112">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="19321-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19321-113">惠?</span><span class="sxs-lookup"><span data-stu-id="19321-113">Requirements</span></span>  
 <span data-ttu-id="19321-114">**标头：** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="19321-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19321-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="19321-115">See Also</span></span>  
 [<span data-ttu-id="19321-116">IDebugAutoAttach 接口</span><span class="sxs-lookup"><span data-stu-id="19321-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
