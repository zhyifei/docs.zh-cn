---
title: FExecuteInAppDomainCallback 函数指针
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3031ce0eb6f23fdf5e5366d33ff075ea7816b0b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649539"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="d3adb-102">FExecuteInAppDomainCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="d3adb-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="d3adb-103">指向以公共语言运行时 (CLR) 以执行托管的代码调用的函数。</span><span class="sxs-lookup"><span data-stu-id="d3adb-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="d3adb-104">中已弃用此函数指针[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3adb-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3adb-105">语法</span><span class="sxs-lookup"><span data-stu-id="d3adb-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3adb-106">参数</span><span class="sxs-lookup"><span data-stu-id="d3adb-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="d3adb-107">[in]指向包含要执行的托管的代码的不透明调用方分配的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="d3adb-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="d3adb-108">分配和此内存的生存期由调用方 (CLR) 控制。</span><span class="sxs-lookup"><span data-stu-id="d3adb-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="d3adb-109">这不是 CLR 托管堆内存。</span><span class="sxs-lookup"><span data-stu-id="d3adb-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3adb-110">要求</span><span class="sxs-lookup"><span data-stu-id="d3adb-110">Requirements</span></span>  
 <span data-ttu-id="d3adb-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3adb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3adb-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3adb-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3adb-113">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="d3adb-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d3adb-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3adb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3adb-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3adb-115">See also</span></span>
- [<span data-ttu-id="d3adb-116">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="d3adb-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
