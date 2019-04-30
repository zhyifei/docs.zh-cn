---
title: ISymUnmanagedReader::GetNamespaces 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 570532433483e9d0a08f4d685087c0736e135390
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993299"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="27a83-102">ISymUnmanagedReader::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="27a83-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="27a83-103">获取全局范围内此符号存储区定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="27a83-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a83-104">语法</span><span class="sxs-lookup"><span data-stu-id="27a83-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27a83-105">参数</span><span class="sxs-lookup"><span data-stu-id="27a83-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="27a83-106">[in]命名空间数组的大小。</span><span class="sxs-lookup"><span data-stu-id="27a83-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="27a83-107">[out]指向一个变量来接收该命名空间列表的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="27a83-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="27a83-108">[out]指向一个变量来接收命名空间列表的指针。</span><span class="sxs-lookup"><span data-stu-id="27a83-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27a83-109">返回值</span><span class="sxs-lookup"><span data-stu-id="27a83-109">Return Value</span></span>  
 <span data-ttu-id="27a83-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="27a83-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27a83-111">要求</span><span class="sxs-lookup"><span data-stu-id="27a83-111">Requirements</span></span>  
 <span data-ttu-id="27a83-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="27a83-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a83-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="27a83-113">See also</span></span>

- [<span data-ttu-id="27a83-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="27a83-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
