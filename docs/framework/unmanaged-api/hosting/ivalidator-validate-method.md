---
title: "IValidator::Validate 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IValidator.Validate
api_location: mscoree.dll
api_type: COM
f1_keywords: Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 722c6acc7e152a78ba28bc2730b2fdc7e0c45eb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="f2cb4-102">IValidator::Validate 方法</span><span class="sxs-lookup"><span data-stu-id="f2cb4-102">IValidator::Validate Method</span></span>
<span data-ttu-id="f2cb4-103">验证指定的可移植可执行 (PE) 或 Microsoft 中间语言 (MSIL) 文件。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2cb4-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2cb4-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2cb4-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="f2cb4-106">[in]指向的指针`IVEHandler`处理验证错误的实例。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="f2cb4-107">[in]指向在其中加载的文件的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="f2cb4-108">[in]按位组合[ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)值，指示应执行的验证。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="f2cb4-109">[in]最大允许在退出验证之前的错误数。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="f2cb4-110">[in]未使用。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="f2cb4-111">[in]一个字符串，指定要验证文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="f2cb4-112">[in]指向在其中存储该文件的内存缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="f2cb4-113">[in]以字节为单位，要验证的文件的大小。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2cb4-114">要求</span><span class="sxs-lookup"><span data-stu-id="f2cb4-114">Requirements</span></span>  
 <span data-ttu-id="f2cb4-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2cb4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2cb4-116">**标头：** IValidator.idl、 IValidator.h</span><span class="sxs-lookup"><span data-stu-id="f2cb4-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="f2cb4-117">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f2cb4-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2cb4-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2cb4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cb4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2cb4-119">See Also</span></span>  
 
