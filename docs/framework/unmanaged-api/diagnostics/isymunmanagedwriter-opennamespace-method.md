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
ms.openlocfilehash: 02f57fdbbc1ea9a391d9c58c7ab49af0ef02f001
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426946"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="6bbbd-102">ISymUnmanagedWriter::OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="6bbbd-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="6bbbd-103">打开一个新的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6bbbd-103">Opens a new namespace.</span></span> <span data-ttu-id="6bbbd-104">定义方法或占用的命名空间的变量之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="6bbbd-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="6bbbd-105">可以嵌套命名空间。</span><span class="sxs-lookup"><span data-stu-id="6bbbd-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bbbd-106">语法</span><span class="sxs-lookup"><span data-stu-id="6bbbd-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bbbd-107">参数</span><span class="sxs-lookup"><span data-stu-id="6bbbd-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6bbbd-108">[in]指向新的命名空间的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="6bbbd-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bbbd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6bbbd-109">Return Value</span></span>  
 <span data-ttu-id="6bbbd-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="6bbbd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bbbd-111">要求</span><span class="sxs-lookup"><span data-stu-id="6bbbd-111">Requirements</span></span>  
 <span data-ttu-id="6bbbd-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6bbbd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bbbd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bbbd-113">See Also</span></span>  
 [<span data-ttu-id="6bbbd-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="6bbbd-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="6bbbd-115">CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="6bbbd-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
