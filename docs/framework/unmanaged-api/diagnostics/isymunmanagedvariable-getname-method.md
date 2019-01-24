---
title: ISymUnmanagedVariable::GetName 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6323b7d94ca32646d3aa63af6d3efc4de95e67fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534509"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="07c2f-102">ISymUnmanagedVariable::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="07c2f-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="07c2f-103">获取此变量的名称。</span><span class="sxs-lookup"><span data-stu-id="07c2f-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07c2f-104">语法</span><span class="sxs-lookup"><span data-stu-id="07c2f-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07c2f-105">参数</span><span class="sxs-lookup"><span data-stu-id="07c2f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="07c2f-106">[in]缓冲区的长度的`pcchName`参数指向。</span><span class="sxs-lookup"><span data-stu-id="07c2f-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="07c2f-107">[out]一个指向`ULONG32`用于接收大小，以字符为单位，以包含名称，包括 null 终止的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="07c2f-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="07c2f-108">[out]存储名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="07c2f-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07c2f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="07c2f-109">Return Value</span></span>  
 <span data-ttu-id="07c2f-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="07c2f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07c2f-111">要求</span><span class="sxs-lookup"><span data-stu-id="07c2f-111">Requirements</span></span>  
 <span data-ttu-id="07c2f-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="07c2f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c2f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="07c2f-113">See also</span></span>
- [<span data-ttu-id="07c2f-114">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="07c2f-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
