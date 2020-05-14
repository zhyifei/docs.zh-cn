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
ms.openlocfilehash: 2cd2238ac67713564922be440ce64a2ebc4bbf44
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396333"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="a47bf-102">ICorPublish::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="a47bf-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="a47bf-103">获取一个表示具有指定标识符的进程的[ICorPublishProcess](icorpublishprocess-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="a47bf-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a47bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="a47bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a47bf-105">参数</span><span class="sxs-lookup"><span data-stu-id="a47bf-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="a47bf-106">中进程的标识符。</span><span class="sxs-lookup"><span data-stu-id="a47bf-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a47bf-107">弄一个指针，指向 `ICorPublishProcess` 表示进程的实例的地址。</span><span class="sxs-lookup"><span data-stu-id="a47bf-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a47bf-108">备注</span><span class="sxs-lookup"><span data-stu-id="a47bf-108">Remarks</span></span>  
 <span data-ttu-id="a47bf-109">`GetProcess`如果进程不存在，或者不是可由当前用户调试的托管进程，则会失败。</span><span class="sxs-lookup"><span data-stu-id="a47bf-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a47bf-110">要求</span><span class="sxs-lookup"><span data-stu-id="a47bf-110">Requirements</span></span>  
 <span data-ttu-id="a47bf-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a47bf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a47bf-112">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="a47bf-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a47bf-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a47bf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a47bf-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a47bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47bf-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a47bf-115">See also</span></span>

- [<span data-ttu-id="a47bf-116">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="a47bf-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
