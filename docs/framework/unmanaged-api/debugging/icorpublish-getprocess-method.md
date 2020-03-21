---
title: ICorPublish::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: 46f047dbec7ff008873540806b76ffe7085086b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178423"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="f562c-102">ICorPublish::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="f562c-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="f562c-103">获取使用指定标识符表示进程的[ICorPublishProcess](icorpublishprocess-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="f562c-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f562c-104">语法</span><span class="sxs-lookup"><span data-stu-id="f562c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f562c-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f562c-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="f562c-106">[在]进程的标识符。</span><span class="sxs-lookup"><span data-stu-id="f562c-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="f562c-107">[出]指向表示进程的`ICorPublishProcess`实例地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f562c-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f562c-108">备注</span><span class="sxs-lookup"><span data-stu-id="f562c-108">Remarks</span></span>  
 <span data-ttu-id="f562c-109">`GetProcess`如果进程不存在，或者不是当前用户可以调试的托管进程，则失败。</span><span class="sxs-lookup"><span data-stu-id="f562c-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f562c-110">要求</span><span class="sxs-lookup"><span data-stu-id="f562c-110">Requirements</span></span>  
 <span data-ttu-id="f562c-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f562c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f562c-112">**标题：** 科尔普布.idl， 科尔普布.h</span><span class="sxs-lookup"><span data-stu-id="f562c-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f562c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f562c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f562c-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f562c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f562c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f562c-115">See also</span></span>

- [<span data-ttu-id="f562c-116">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="f562c-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
