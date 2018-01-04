---
title: "ISymUnmanagedVariable::GetName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a50fe9d0fddc6239eb03c9007ec2ca64d7d27ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="81153-102">ISymUnmanagedVariable::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="81153-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="81153-103">获取此变量的名称。</span><span class="sxs-lookup"><span data-stu-id="81153-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81153-104">语法</span><span class="sxs-lookup"><span data-stu-id="81153-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81153-105">参数</span><span class="sxs-lookup"><span data-stu-id="81153-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="81153-106">[in]缓冲区的长度，`pcchName`参数指向。</span><span class="sxs-lookup"><span data-stu-id="81153-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="81153-107">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含文件的名称，包括 null 终止所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="81153-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="81153-108">[out]存储的名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="81153-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81153-109">返回值</span><span class="sxs-lookup"><span data-stu-id="81153-109">Return Value</span></span>  
 <span data-ttu-id="81153-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="81153-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81153-111">惠?</span><span class="sxs-lookup"><span data-stu-id="81153-111">Requirements</span></span>  
 <span data-ttu-id="81153-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="81153-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81153-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="81153-113">See Also</span></span>  
 [<span data-ttu-id="81153-114">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="81153-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
