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
ms.openlocfilehash: d8e5ab607f9310341ded482b35f02f3845926328
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008555"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="20e6c-102">IValidator 接口</span><span class="sxs-lookup"><span data-stu-id="20e6c-102">IValidator Interface</span></span>
<span data-ttu-id="20e6c-103">提供用于验证可移植可执行（PE）映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="20e6c-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20e6c-104">方法</span><span class="sxs-lookup"><span data-stu-id="20e6c-104">Methods</span></span>  
  
|<span data-ttu-id="20e6c-105">方法</span><span class="sxs-lookup"><span data-stu-id="20e6c-105">Method</span></span>|<span data-ttu-id="20e6c-106">说明</span><span class="sxs-lookup"><span data-stu-id="20e6c-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="20e6c-107">验证</span><span class="sxs-lookup"><span data-stu-id="20e6c-107">Validate</span></span>|<span data-ttu-id="20e6c-108">验证指定的 PE 或 Microsoft 中间语言（MSIL）文件。</span><span class="sxs-lookup"><span data-stu-id="20e6c-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="20e6c-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="20e6c-109">FormatEventInfo</span></span>|<span data-ttu-id="20e6c-110">获取与指定的验证错误相对应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="20e6c-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20e6c-111">要求</span><span class="sxs-lookup"><span data-stu-id="20e6c-111">Requirements</span></span>  
 <span data-ttu-id="20e6c-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20e6c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20e6c-113">**标头：** IValidator，IValidator</span><span class="sxs-lookup"><span data-stu-id="20e6c-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="20e6c-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="20e6c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20e6c-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20e6c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e6c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20e6c-116">See also</span></span>

- [<span data-ttu-id="20e6c-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="20e6c-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="20e6c-118">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="20e6c-118">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
