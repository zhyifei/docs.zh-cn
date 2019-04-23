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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0739cc38d1f12967f0daef2d6828e04a256ade6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201840"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="d1a7c-102">ISymUnmanagedWriter::UsingNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="d1a7c-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="d1a7c-103">指定当前打开的词法范围内，使用给定的完全限定的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="d1a7c-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="d1a7c-104">将从当前打开的作用域继承的所有作用域内使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d1a7c-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="d1a7c-105">关闭当前作用域也将停止使用此命名空间。</span><span class="sxs-lookup"><span data-stu-id="d1a7c-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1a7c-106">语法</span><span class="sxs-lookup"><span data-stu-id="d1a7c-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1a7c-107">参数</span><span class="sxs-lookup"><span data-stu-id="d1a7c-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="d1a7c-108">[in]指向命名空间的完全限定名称的指针。</span><span class="sxs-lookup"><span data-stu-id="d1a7c-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1a7c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d1a7c-109">Return Value</span></span>  
 <span data-ttu-id="d1a7c-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="d1a7c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1a7c-111">要求</span><span class="sxs-lookup"><span data-stu-id="d1a7c-111">Requirements</span></span>  
 <span data-ttu-id="d1a7c-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d1a7c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a7c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1a7c-113">See also</span></span>

- [<span data-ttu-id="d1a7c-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="d1a7c-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
