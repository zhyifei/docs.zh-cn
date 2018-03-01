---
title: "ISymUnmanagedWriter::UsingNamespace 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d02a36a43e8a831fbbef051f5898696d4d8e04c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="14fbe-102">ISymUnmanagedWriter::UsingNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="14fbe-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="14fbe-103">指定当前打开的词法范围内，使用给定的完全限定的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="14fbe-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="14fbe-104">将在所有作用域都继承自当前打开的范围内使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="14fbe-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="14fbe-105">关闭当前作用域也将停止使用此命名空间。</span><span class="sxs-lookup"><span data-stu-id="14fbe-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14fbe-106">语法</span><span class="sxs-lookup"><span data-stu-id="14fbe-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14fbe-107">参数</span><span class="sxs-lookup"><span data-stu-id="14fbe-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="14fbe-108">[in]指向命名空间的完全限定名称的指针。</span><span class="sxs-lookup"><span data-stu-id="14fbe-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14fbe-109">返回值</span><span class="sxs-lookup"><span data-stu-id="14fbe-109">Return Value</span></span>  
 <span data-ttu-id="14fbe-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="14fbe-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14fbe-111">惠?</span><span class="sxs-lookup"><span data-stu-id="14fbe-111">Requirements</span></span>  
 <span data-ttu-id="14fbe-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="14fbe-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14fbe-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="14fbe-113">See Also</span></span>  
 [<span data-ttu-id="14fbe-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="14fbe-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
