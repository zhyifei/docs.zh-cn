---
title: IValidator::Validate 方法
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 8ae47eac713fbee30ea543538957b12460b8e1fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123271"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="23049-102">IValidator::Validate 方法</span><span class="sxs-lookup"><span data-stu-id="23049-102">IValidator::Validate Method</span></span>
<span data-ttu-id="23049-103">验证指定的可移植可执行（PE）或 Microsoft 中间语言（MSIL）文件。</span><span class="sxs-lookup"><span data-stu-id="23049-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23049-104">语法</span><span class="sxs-lookup"><span data-stu-id="23049-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="23049-105">参数</span><span class="sxs-lookup"><span data-stu-id="23049-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="23049-106">中指向处理验证错误的 `IVEHandler` 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="23049-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="23049-107">中一个指针，指向要在其中加载文件的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="23049-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="23049-108">中[ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md)值的按位组合，指示应执行的验证。</span><span class="sxs-lookup"><span data-stu-id="23049-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="23049-109">中在退出验证之前允许的最大错误数。</span><span class="sxs-lookup"><span data-stu-id="23049-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="23049-110">中不使用。</span><span class="sxs-lookup"><span data-stu-id="23049-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="23049-111">中一个字符串，指定要验证的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="23049-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="23049-112">中指向存储文件的内存缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="23049-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="23049-113">中要验证的文件的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="23049-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23049-114">要求</span><span class="sxs-lookup"><span data-stu-id="23049-114">Requirements</span></span>  
 <span data-ttu-id="23049-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23049-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23049-116">**标头：** IValidator，IValidator</span><span class="sxs-lookup"><span data-stu-id="23049-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="23049-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="23049-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23049-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23049-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
