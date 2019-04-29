---
title: IValidator 接口
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f516bf1f19e4d4a77e2d6af834a1c3d4e34c327
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765344"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="8de01-102">IValidator 接口</span><span class="sxs-lookup"><span data-stu-id="8de01-102">IValidator Interface</span></span>
<span data-ttu-id="8de01-103">提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="8de01-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8de01-104">方法</span><span class="sxs-lookup"><span data-stu-id="8de01-104">Methods</span></span>  
  
|<span data-ttu-id="8de01-105">方法</span><span class="sxs-lookup"><span data-stu-id="8de01-105">Method</span></span>|<span data-ttu-id="8de01-106">描述</span><span class="sxs-lookup"><span data-stu-id="8de01-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8de01-107">Validate</span><span class="sxs-lookup"><span data-stu-id="8de01-107">Validate</span></span>|<span data-ttu-id="8de01-108">验证指定的 PE 或 Microsoft 中间语言 (MSIL) 文件。</span><span class="sxs-lookup"><span data-stu-id="8de01-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="8de01-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="8de01-109">FormatEventInfo</span></span>|<span data-ttu-id="8de01-110">获取对应于指定的验证错误的错误消息。</span><span class="sxs-lookup"><span data-stu-id="8de01-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8de01-111">要求</span><span class="sxs-lookup"><span data-stu-id="8de01-111">Requirements</span></span>  
 <span data-ttu-id="8de01-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8de01-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8de01-113">**标头：** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="8de01-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="8de01-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8de01-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8de01-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8de01-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de01-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8de01-116">See also</span></span>

- [<span data-ttu-id="8de01-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="8de01-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="8de01-118">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="8de01-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
