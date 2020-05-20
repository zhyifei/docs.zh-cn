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
ms.openlocfilehash: 57508a2df3a49c39d25347f2a3038442c37278da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616757"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="8e4d5-102">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="8e4d5-102">CoInitializeEE Function</span></span>
<span data-ttu-id="8e4d5-103">确保将公共语言运行时执行引擎加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="8e4d5-104">此函数在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="8e4d5-105">改为使用[ICLRRuntimeHost：： Start](iclrruntimehost-start-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-105">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e4d5-106">语法</span><span class="sxs-lookup"><span data-stu-id="8e4d5-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e4d5-107">参数</span><span class="sxs-lookup"><span data-stu-id="8e4d5-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="8e4d5-108">中[COINITIEE](../metadata/coinitiee-enumeration.md)枚举常量之一。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-108">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e4d5-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8e4d5-109">Return Value</span></span>  
 <span data-ttu-id="8e4d5-110">此方法返回 Winerror.h 中定义的标准 COM 错误代码，以及下表中的值。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="8e4d5-111">返回代码</span><span class="sxs-lookup"><span data-stu-id="8e4d5-111">Return code</span></span>|<span data-ttu-id="8e4d5-112">说明</span><span class="sxs-lookup"><span data-stu-id="8e4d5-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="8e4d5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e4d5-113">S_OK</span></span>|<span data-ttu-id="8e4d5-114">已成功加载执行引擎。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="8e4d5-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8e4d5-115">S_FALSE</span></span>|<span data-ttu-id="8e4d5-116">已经加载了执行引擎。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="8e4d5-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e4d5-117">E_FAIL</span></span>|<span data-ttu-id="8e4d5-118">未能加载执行引擎。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e4d5-119">备注</span><span class="sxs-lookup"><span data-stu-id="8e4d5-119">Remarks</span></span>  
 <span data-ttu-id="8e4d5-120">此方法加载尚未加载的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e4d5-121">要求</span><span class="sxs-lookup"><span data-stu-id="8e4d5-121">Requirements</span></span>  
 <span data-ttu-id="8e4d5-122">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e4d5-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e4d5-123">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8e4d5-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e4d5-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8e4d5-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8e4d5-125">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e4d5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e4d5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e4d5-126">See also</span></span>

- [<span data-ttu-id="8e4d5-127">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="8e4d5-127">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
