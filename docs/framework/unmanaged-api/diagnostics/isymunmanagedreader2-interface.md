---
title: "ISymUnmanagedReader2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2
helpviewer_keywords: ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b23e166249659b94d454070c01c003495d1018a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="f3db1-102">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="f3db1-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="f3db1-103">表示提供对文档、 方法和符号存储区内的变量的访问的符号读取器。</span><span class="sxs-lookup"><span data-stu-id="f3db1-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="f3db1-104">此接口扩展[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f3db1-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3db1-105">方法</span><span class="sxs-lookup"><span data-stu-id="f3db1-105">Methods</span></span>  
  
|<span data-ttu-id="f3db1-106">方法</span><span class="sxs-lookup"><span data-stu-id="f3db1-106">Method</span></span>|<span data-ttu-id="f3db1-107">描述</span><span class="sxs-lookup"><span data-stu-id="f3db1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3db1-108">GetMethodByVersionPreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="f3db1-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="f3db1-109">获取符号读取器方法，在给定方法标记和编辑并继续的版本号。</span><span class="sxs-lookup"><span data-stu-id="f3db1-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="f3db1-110">GetMethodsInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="f3db1-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="f3db1-111">获取每个方法，提供的文档中包含行信息。</span><span class="sxs-lookup"><span data-stu-id="f3db1-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="f3db1-112">GetSymAttributePreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="f3db1-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="f3db1-113">获取基于其名称的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="f3db1-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3db1-114">要求</span><span class="sxs-lookup"><span data-stu-id="f3db1-114">Requirements</span></span>  
 <span data-ttu-id="f3db1-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f3db1-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3db1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3db1-116">See Also</span></span>  
 [<span data-ttu-id="f3db1-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="f3db1-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f3db1-118">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="f3db1-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
