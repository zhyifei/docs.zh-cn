---
title: "ISymUnmanagedReader::GetNamespaces 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetNamespaces
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9db8875acfd4df2cd889cc2e6d606aba252fa33f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="b4be2-102">ISymUnmanagedReader::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="b4be2-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="b4be2-103">获取在此符号存储区中的全局范围内定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b4be2-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4be2-104">语法</span><span class="sxs-lookup"><span data-stu-id="b4be2-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4be2-105">参数</span><span class="sxs-lookup"><span data-stu-id="b4be2-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="b4be2-106">[in]命名空间数组的大小。</span><span class="sxs-lookup"><span data-stu-id="b4be2-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="b4be2-107">[out]指向接收命名空间列表的长度的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="b4be2-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="b4be2-108">[out]指向接收的命名空间列表的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="b4be2-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4be2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b4be2-109">Return Value</span></span>  
 <span data-ttu-id="b4be2-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="b4be2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4be2-111">惠?</span><span class="sxs-lookup"><span data-stu-id="b4be2-111">Requirements</span></span>  
 <span data-ttu-id="b4be2-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b4be2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4be2-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4be2-113">See Also</span></span>  
 [<span data-ttu-id="b4be2-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="b4be2-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
