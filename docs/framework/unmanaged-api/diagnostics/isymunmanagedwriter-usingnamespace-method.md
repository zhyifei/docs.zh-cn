---
title: ISymUnmanagedWriter::UsingNamespace 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
ms.openlocfilehash: cb0af78092822875204f45ec3dca1484e5b5fc90
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427465"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="f1e39-102">ISymUnmanagedWriter::UsingNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="f1e39-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="f1e39-103">指定在当前打开的词法范围内使用给定的完全限定的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="f1e39-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="f1e39-104">命名空间将在从当前打开的作用域继承的所有范围内使用。</span><span class="sxs-lookup"><span data-stu-id="f1e39-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="f1e39-105">关闭当前作用域也将停止使用该命名空间。</span><span class="sxs-lookup"><span data-stu-id="f1e39-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1e39-106">语法</span><span class="sxs-lookup"><span data-stu-id="f1e39-106">Syntax</span></span>  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1e39-107">参数</span><span class="sxs-lookup"><span data-stu-id="f1e39-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="f1e39-108">中指向命名空间的完全限定名称的指针。</span><span class="sxs-lookup"><span data-stu-id="f1e39-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1e39-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f1e39-109">Return Value</span></span>  
 <span data-ttu-id="f1e39-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="f1e39-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1e39-111">要求</span><span class="sxs-lookup"><span data-stu-id="f1e39-111">Requirements</span></span>  
 <span data-ttu-id="f1e39-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="f1e39-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e39-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1e39-113">See also</span></span>

- [<span data-ttu-id="f1e39-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="f1e39-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
