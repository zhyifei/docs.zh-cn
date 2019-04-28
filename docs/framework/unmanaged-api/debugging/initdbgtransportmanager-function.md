---
title: InitDbgTransportManager 函数
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74cb2c7d1f79d23e1331cc7192ba2d6acfd9835c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761645"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="21d81-102">InitDbgTransportManager 函数</span><span class="sxs-lookup"><span data-stu-id="21d81-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="21d81-103">初始化传输管理器以连接到进程和运行时枚举的远程目标。</span><span class="sxs-lookup"><span data-stu-id="21d81-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d81-104">语法</span><span class="sxs-lookup"><span data-stu-id="21d81-104">Syntax</span></span>  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="21d81-105">返回值</span><span class="sxs-lookup"><span data-stu-id="21d81-105">Return Value</span></span>  
 <span data-ttu-id="21d81-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="21d81-106">S_OK</span></span>  
 <span data-ttu-id="21d81-107">成功。</span><span class="sxs-lookup"><span data-stu-id="21d81-107">Success.</span></span>  
  
 <span data-ttu-id="21d81-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="21d81-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="21d81-109">该函数不能为传输管理器分配内存。</span><span class="sxs-lookup"><span data-stu-id="21d81-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="21d81-110">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="21d81-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="21d81-111">其他故障。</span><span class="sxs-lookup"><span data-stu-id="21d81-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21d81-112">要求</span><span class="sxs-lookup"><span data-stu-id="21d81-112">Requirements</span></span>  
 <span data-ttu-id="21d81-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21d81-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21d81-114">**标头：** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="21d81-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="21d81-115">**库：** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="21d81-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="21d81-116">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="21d81-116">**.NET Framework Versions:** 3.5 SP1</span></span>
