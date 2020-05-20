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
ms.openlocfilehash: 294b82efd66704014aab1b73171afe9165f17664
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616445"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="382a3-102">CreateICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="382a3-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="382a3-103">创建[ICeeFileGen](iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="382a3-103">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="382a3-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="382a3-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="382a3-105">语法</span><span class="sxs-lookup"><span data-stu-id="382a3-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="382a3-106">参数</span><span class="sxs-lookup"><span data-stu-id="382a3-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="382a3-107">弄指向新对象的地址的指针 `ICeeFileGen` 。</span><span class="sxs-lookup"><span data-stu-id="382a3-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="382a3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="382a3-108">Return Value</span></span>  
 <span data-ttu-id="382a3-109">此方法返回标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="382a3-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="382a3-110">备注</span><span class="sxs-lookup"><span data-stu-id="382a3-110">Remarks</span></span>  
 <span data-ttu-id="382a3-111">`ICeeFileGen`对象用于创建公共语言运行时（CLR）可移植可执行（PE）文件。</span><span class="sxs-lookup"><span data-stu-id="382a3-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="382a3-112">完成后，调用[DestroyICeeFileGen](destroyiceefilegen-function.md)函数以销毁 `ICeeFileGen` 对象。</span><span class="sxs-lookup"><span data-stu-id="382a3-112">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="382a3-113">要求</span><span class="sxs-lookup"><span data-stu-id="382a3-113">Requirements</span></span>  
 <span data-ttu-id="382a3-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="382a3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="382a3-115">**标头：** ICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="382a3-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="382a3-116">**库：** MSCorPE</span><span class="sxs-lookup"><span data-stu-id="382a3-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="382a3-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="382a3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="382a3-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="382a3-118">See also</span></span>

- [<span data-ttu-id="382a3-119">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="382a3-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
