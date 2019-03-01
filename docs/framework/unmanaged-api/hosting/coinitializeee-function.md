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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca85a12191db51818da2a08910dc9524d1ac9498
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211814"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="97f90-102">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="97f90-102">CoInitializeEE Function</span></span>
<span data-ttu-id="97f90-103">确保公共语言运行时执行引擎已加载到进程。</span><span class="sxs-lookup"><span data-stu-id="97f90-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="97f90-104">此函数已弃用在[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97f90-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="97f90-105">使用[iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="97f90-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f90-106">语法</span><span class="sxs-lookup"><span data-stu-id="97f90-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97f90-107">参数</span><span class="sxs-lookup"><span data-stu-id="97f90-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="97f90-108">[in]之一[COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md)枚举常量。</span><span class="sxs-lookup"><span data-stu-id="97f90-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97f90-109">返回值</span><span class="sxs-lookup"><span data-stu-id="97f90-109">Return Value</span></span>  
 <span data-ttu-id="97f90-110">Winerror.h 和下表中的值中定义，此方法将返回标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="97f90-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="97f90-111">返回代码</span><span class="sxs-lookup"><span data-stu-id="97f90-111">Return code</span></span>|<span data-ttu-id="97f90-112">描述</span><span class="sxs-lookup"><span data-stu-id="97f90-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="97f90-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="97f90-113">S_OK</span></span>|<span data-ttu-id="97f90-114">执行引擎已成功加载。</span><span class="sxs-lookup"><span data-stu-id="97f90-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="97f90-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="97f90-115">S_FALSE</span></span>|<span data-ttu-id="97f90-116">执行引擎已加载。</span><span class="sxs-lookup"><span data-stu-id="97f90-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="97f90-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97f90-117">E_FAIL</span></span>|<span data-ttu-id="97f90-118">无法加载执行引擎。</span><span class="sxs-lookup"><span data-stu-id="97f90-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97f90-119">备注</span><span class="sxs-lookup"><span data-stu-id="97f90-119">Remarks</span></span>  
 <span data-ttu-id="97f90-120">如果它先前加载，则此方法加载的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="97f90-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97f90-121">要求</span><span class="sxs-lookup"><span data-stu-id="97f90-121">Requirements</span></span>  
 <span data-ttu-id="97f90-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97f90-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97f90-123">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="97f90-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="97f90-124">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="97f90-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="97f90-125">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97f90-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f90-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="97f90-126">See also</span></span>
- [<span data-ttu-id="97f90-127">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="97f90-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
