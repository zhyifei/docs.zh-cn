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
ms.openlocfilehash: a86a93db6058a8fda42e837388f7fa4cf5c765c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="079b6-102">ISymUnmanagedVariable::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="079b6-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="079b6-103">获取此变量的名称。</span><span class="sxs-lookup"><span data-stu-id="079b6-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="079b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="079b6-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="079b6-105">参数</span><span class="sxs-lookup"><span data-stu-id="079b6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="079b6-106">[in]缓冲区的长度，`pcchName`参数指向。</span><span class="sxs-lookup"><span data-stu-id="079b6-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="079b6-107">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含文件的名称，包括 null 终止所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="079b6-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="079b6-108">[out]存储的名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="079b6-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="079b6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="079b6-109">Return Value</span></span>  
 <span data-ttu-id="079b6-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="079b6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="079b6-111">要求</span><span class="sxs-lookup"><span data-stu-id="079b6-111">Requirements</span></span>  
 <span data-ttu-id="079b6-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="079b6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="079b6-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="079b6-113">See Also</span></span>  
 [<span data-ttu-id="079b6-114">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="079b6-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
