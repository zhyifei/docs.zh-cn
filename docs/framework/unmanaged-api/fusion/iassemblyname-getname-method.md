---
title: IAssemblyName::GetName 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
ms.openlocfilehash: 5f758d76d779cff7db119e69dc1cf3342071f1c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134339"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="6ca2b-102">IAssemblyName::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="6ca2b-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="6ca2b-103">获取此[IAssemblyName](iassemblyname-interface.md)对象所引用的程序集的简单、未加密名称。</span><span class="sxs-lookup"><span data-stu-id="6ca2b-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ca2b-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ca2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ca2b-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ca2b-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="6ca2b-106">[in，out]宽字符 `pwzName` 的大小，包括 null 终止符。</span><span class="sxs-lookup"><span data-stu-id="6ca2b-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="6ca2b-107">弄用于保存所引用程序集的名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6ca2b-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ca2b-108">要求</span><span class="sxs-lookup"><span data-stu-id="6ca2b-108">Requirements</span></span>  
 <span data-ttu-id="6ca2b-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ca2b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ca2b-110">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="6ca2b-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6ca2b-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ca2b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca2b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ca2b-112">See also</span></span>

- [<span data-ttu-id="6ca2b-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="6ca2b-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
