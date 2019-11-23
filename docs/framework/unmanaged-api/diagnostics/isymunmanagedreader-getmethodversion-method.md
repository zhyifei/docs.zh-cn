---
title: ISymUnmanagedReader::GetMethodVersion 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: fcaf748413321f684336543e60f735af69894b51
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436007"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="ed9fa-102">ISymUnmanagedReader::GetMethodVersion 方法</span><span class="sxs-lookup"><span data-stu-id="ed9fa-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="ed9fa-103">Gets the method version.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-103">Gets the method version.</span></span> <span data-ttu-id="ed9fa-104">The method version starts at 1 and is incremented each time the method is recompiled.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="ed9fa-105">Recompilation can happen without changes to the method.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed9fa-106">语法</span><span class="sxs-lookup"><span data-stu-id="ed9fa-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed9fa-107">参数</span><span class="sxs-lookup"><span data-stu-id="ed9fa-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="ed9fa-108">[in] The method for which to get the version.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="ed9fa-109">[out] A pointer to a variable that receives the method version.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed9fa-110">返回值</span><span class="sxs-lookup"><span data-stu-id="ed9fa-110">Return Value</span></span>  
 <span data-ttu-id="ed9fa-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="ed9fa-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed9fa-112">要求</span><span class="sxs-lookup"><span data-stu-id="ed9fa-112">Requirements</span></span>  
 <span data-ttu-id="ed9fa-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ed9fa-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed9fa-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed9fa-114">See also</span></span>

- [<span data-ttu-id="ed9fa-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="ed9fa-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
