---
title: CreateAssemblyNameObject 函数
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
ms.openlocfilehash: 00345f6c95c67f0494aa721c662f56a9e98cdd7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108712"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="3a195-102">CreateAssemblyNameObject 函数</span><span class="sxs-lookup"><span data-stu-id="3a195-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="3a195-103">获取一个接口指针，该指针指向表示具有指定名称的程序集的唯一标识的[IAssemblyName](iassemblyname-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="3a195-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a195-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a195-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a195-105">参数</span><span class="sxs-lookup"><span data-stu-id="3a195-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="3a195-106">弄返回的 `IAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="3a195-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="3a195-107">中要为其创建新 `IAssemblyName` 实例的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="3a195-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3a195-108">中要传递给对象构造函数的标志。</span><span class="sxs-lookup"><span data-stu-id="3a195-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="3a195-109">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="3a195-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3a195-110">`pvReserved` 必须为空引用。</span><span class="sxs-lookup"><span data-stu-id="3a195-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a195-111">要求</span><span class="sxs-lookup"><span data-stu-id="3a195-111">Requirements</span></span>  
 <span data-ttu-id="3a195-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3a195-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a195-113">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="3a195-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3a195-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3a195-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a195-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a195-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a195-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a195-116">See also</span></span>

- [<span data-ttu-id="3a195-117">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="3a195-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="3a195-118">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="3a195-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
