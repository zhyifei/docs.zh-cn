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
ms.openlocfilehash: 458faedea418e626a6494ca2afcdbf0e034472e8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447729"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="e39dc-102">ISymUnmanagedReader::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="e39dc-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="e39dc-103">获取在此符号存储区的全局范围内定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e39dc-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e39dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="e39dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e39dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="e39dc-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="e39dc-106">中命名空间数组的大小。</span><span class="sxs-lookup"><span data-stu-id="e39dc-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="e39dc-107">弄指向一个变量的指针，该变量接收命名空间列表的长度。</span><span class="sxs-lookup"><span data-stu-id="e39dc-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="e39dc-108">弄指向接收命名空间列表的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="e39dc-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e39dc-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e39dc-109">Return Value</span></span>  
 <span data-ttu-id="e39dc-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="e39dc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e39dc-111">要求</span><span class="sxs-lookup"><span data-stu-id="e39dc-111">Requirements</span></span>  
 <span data-ttu-id="e39dc-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e39dc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e39dc-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e39dc-113">See also</span></span>

- [<span data-ttu-id="e39dc-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="e39dc-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
