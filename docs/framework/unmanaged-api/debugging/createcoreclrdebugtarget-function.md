---
title: CreateCoreClrDebugTarget 函数
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: 2271611b5cbbfe487e5798be0429ed94c227a67f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860884"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="c387e-102">CreateCoreClrDebugTarget 函数</span><span class="sxs-lookup"><span data-stu-id="c387e-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="c387e-103">创建与远程计算机上运行的调试器代理的连接，并返回一个[ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)对象，该对象可用于查询远程计算机上正在运行的进程和已加载的运行时。</span><span class="sxs-lookup"><span data-stu-id="c387e-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c387e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c387e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c387e-105">参数</span><span class="sxs-lookup"><span data-stu-id="c387e-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="c387e-106">[in] 远程目标计算机的 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="c387e-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="c387e-107">弄指向将创建的[ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c387e-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c387e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c387e-108">Return Value</span></span>  
 <span data-ttu-id="c387e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="c387e-109">S_OK</span></span>  
 <span data-ttu-id="c387e-110">已成功确定该进程中的 CLR 的数目，并已正确填写相应的句柄数组和路径数组。</span><span class="sxs-lookup"><span data-stu-id="c387e-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="c387e-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c387e-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c387e-112">无法为 `ppTarget` 分配足够的内存。</span><span class="sxs-lookup"><span data-stu-id="c387e-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="c387e-113">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="c387e-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="c387e-114">其他故障。</span><span class="sxs-lookup"><span data-stu-id="c387e-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c387e-115">要求</span><span class="sxs-lookup"><span data-stu-id="c387e-115">Requirements</span></span>  
 <span data-ttu-id="c387e-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c387e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c387e-117">**标头：** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="c387e-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c387e-118">**库：** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="c387e-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c387e-119">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c387e-119">**.NET Framework Versions:** 3.5 SP1</span></span>
