---
title: ISymUnmanagedWriter::OpenNamespace 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1585acce8bba0dff327c961f5e32ef6b46794401
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126329"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="11a6e-102">ISymUnmanagedWriter::OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="11a6e-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="11a6e-103">打开一个新的命名空间。</span><span class="sxs-lookup"><span data-stu-id="11a6e-103">Opens a new namespace.</span></span> <span data-ttu-id="11a6e-104">定义一个命名空间的方法或变量之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="11a6e-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="11a6e-105">可以嵌套命名空间。</span><span class="sxs-lookup"><span data-stu-id="11a6e-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a6e-106">语法</span><span class="sxs-lookup"><span data-stu-id="11a6e-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11a6e-107">参数</span><span class="sxs-lookup"><span data-stu-id="11a6e-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="11a6e-108">[in]一个指向新的命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="11a6e-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11a6e-109">返回值</span><span class="sxs-lookup"><span data-stu-id="11a6e-109">Return Value</span></span>  
 <span data-ttu-id="11a6e-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="11a6e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a6e-111">要求</span><span class="sxs-lookup"><span data-stu-id="11a6e-111">Requirements</span></span>  
 <span data-ttu-id="11a6e-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="11a6e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a6e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="11a6e-113">See also</span></span>

- [<span data-ttu-id="11a6e-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="11a6e-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="11a6e-115">CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="11a6e-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
