---
title: IDebugAutoAttach::AutoAttach 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5064e66708044d82e3a097c8235b5b28a3412200
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077129"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="c374d-102">IDebugAutoAttach::AutoAttach 方法</span><span class="sxs-lookup"><span data-stu-id="c374d-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="c374d-103">执行服务器调用调试器自动附加。</span><span class="sxs-lookup"><span data-stu-id="c374d-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c374d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c374d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c374d-105">参数</span><span class="sxs-lookup"><span data-stu-id="c374d-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="c374d-106">[in]始终设置为`GUID_NULL`。</span><span class="sxs-lookup"><span data-stu-id="c374d-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="c374d-107">[in]进程 ID，通常情况下检索与`GetCurrentProcessId`函数。</span><span class="sxs-lookup"><span data-stu-id="c374d-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="c374d-108">[in]程序类型： `AUTOATTACH_PROGRAM_WIN32`， `AUTOATTACH_PROGRAM_COMPLUS`，或`AUTOATTACH_PROGRAM_UNKNOWN`。</span><span class="sxs-lookup"><span data-stu-id="c374d-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="c374d-109">[in]程序 id。</span><span class="sxs-lookup"><span data-stu-id="c374d-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="c374d-110">[in]Debug 谓词由传递的字符串。</span><span class="sxs-lookup"><span data-stu-id="c374d-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c374d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="c374d-111">Return Value</span></span>  
 <span data-ttu-id="c374d-112">如果该方法成功，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="c374d-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c374d-113">要求</span><span class="sxs-lookup"><span data-stu-id="c374d-113">Requirements</span></span>  
 <span data-ttu-id="c374d-114">**标头：** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="c374d-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c374d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c374d-115">See also</span></span>

- [<span data-ttu-id="c374d-116">IDebugAutoAttach 接口</span><span class="sxs-lookup"><span data-stu-id="c374d-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
