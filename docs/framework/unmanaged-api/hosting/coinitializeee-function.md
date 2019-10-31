---
title: CoInitializeEE 函数
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 9e90772ae8c3e6be5744fcccc9901123df871831
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131945"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="fb172-102">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="fb172-102">CoInitializeEE Function</span></span>
<span data-ttu-id="fb172-103">确保将公共语言运行时执行引擎加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="fb172-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="fb172-104">此函数在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="fb172-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="fb172-105">改为使用[ICLRRuntimeHost：： Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fb172-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb172-106">语法</span><span class="sxs-lookup"><span data-stu-id="fb172-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb172-107">参数</span><span class="sxs-lookup"><span data-stu-id="fb172-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="fb172-108">中[COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md)枚举常量之一。</span><span class="sxs-lookup"><span data-stu-id="fb172-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb172-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fb172-109">Return Value</span></span>  
 <span data-ttu-id="fb172-110">此方法返回 Winerror.h 中定义的标准 COM 错误代码，以及下表中的值。</span><span class="sxs-lookup"><span data-stu-id="fb172-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="fb172-111">返回代码</span><span class="sxs-lookup"><span data-stu-id="fb172-111">Return code</span></span>|<span data-ttu-id="fb172-112">描述</span><span class="sxs-lookup"><span data-stu-id="fb172-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fb172-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb172-113">S_OK</span></span>|<span data-ttu-id="fb172-114">已成功加载执行引擎。</span><span class="sxs-lookup"><span data-stu-id="fb172-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="fb172-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fb172-115">S_FALSE</span></span>|<span data-ttu-id="fb172-116">已经加载了执行引擎。</span><span class="sxs-lookup"><span data-stu-id="fb172-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="fb172-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb172-117">E_FAIL</span></span>|<span data-ttu-id="fb172-118">未能加载执行引擎。</span><span class="sxs-lookup"><span data-stu-id="fb172-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb172-119">备注</span><span class="sxs-lookup"><span data-stu-id="fb172-119">Remarks</span></span>  
 <span data-ttu-id="fb172-120">此方法加载尚未加载的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="fb172-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb172-121">要求</span><span class="sxs-lookup"><span data-stu-id="fb172-121">Requirements</span></span>  
 <span data-ttu-id="fb172-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb172-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb172-123">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="fb172-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb172-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="fb172-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb172-125">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb172-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb172-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb172-126">See also</span></span>

- [<span data-ttu-id="fb172-127">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="fb172-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
