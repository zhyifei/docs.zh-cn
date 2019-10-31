---
title: CreateICeeFileGen 函数
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: de27851b4afc3eccad46531848c68723bff346d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136823"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="3e48f-102">CreateICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="3e48f-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="3e48f-103">创建[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="3e48f-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="3e48f-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="3e48f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e48f-105">语法</span><span class="sxs-lookup"><span data-stu-id="3e48f-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e48f-106">参数</span><span class="sxs-lookup"><span data-stu-id="3e48f-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="3e48f-107">弄指向新的 `ICeeFileGen` 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3e48f-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e48f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3e48f-108">Return Value</span></span>  
 <span data-ttu-id="3e48f-109">此方法返回标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="3e48f-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e48f-110">备注</span><span class="sxs-lookup"><span data-stu-id="3e48f-110">Remarks</span></span>  
 <span data-ttu-id="3e48f-111">`ICeeFileGen` 对象用于创建公共语言运行时（CLR）可移植可执行（PE）文件。</span><span class="sxs-lookup"><span data-stu-id="3e48f-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="3e48f-112">完成后，调用[DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)函数以销毁 `ICeeFileGen` 对象。</span><span class="sxs-lookup"><span data-stu-id="3e48f-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e48f-113">要求</span><span class="sxs-lookup"><span data-stu-id="3e48f-113">Requirements</span></span>  
 <span data-ttu-id="3e48f-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e48f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e48f-115">**标头：** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="3e48f-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="3e48f-116">**库：** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="3e48f-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="3e48f-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e48f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e48f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e48f-118">See also</span></span>

- [<span data-ttu-id="3e48f-119">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="3e48f-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
