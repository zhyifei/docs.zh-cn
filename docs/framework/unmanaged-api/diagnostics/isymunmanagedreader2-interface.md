---
title: ISymUnmanagedReader2 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08695c4e5df6aaa63bedecf68b741302e5ddd8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524933"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="72b9f-102">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="72b9f-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="72b9f-103">表示提供对文档、 方法和符号存储区中的变量的访问的符号读取器。</span><span class="sxs-lookup"><span data-stu-id="72b9f-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="72b9f-104">此接口扩展[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="72b9f-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72b9f-105">方法</span><span class="sxs-lookup"><span data-stu-id="72b9f-105">Methods</span></span>  
  
|<span data-ttu-id="72b9f-106">方法</span><span class="sxs-lookup"><span data-stu-id="72b9f-106">Method</span></span>|<span data-ttu-id="72b9f-107">描述</span><span class="sxs-lookup"><span data-stu-id="72b9f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72b9f-108">GetMethodByVersionPreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="72b9f-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="72b9f-109">获取符号读取器方法，给定一个方法标记和编辑并继续的版本号。</span><span class="sxs-lookup"><span data-stu-id="72b9f-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="72b9f-110">GetMethodsInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="72b9f-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="72b9f-111">获取每个方法中提供的文档包含行信息。</span><span class="sxs-lookup"><span data-stu-id="72b9f-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="72b9f-112">GetSymAttributePreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="72b9f-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="72b9f-113">获取根据其名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="72b9f-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72b9f-114">要求</span><span class="sxs-lookup"><span data-stu-id="72b9f-114">Requirements</span></span>  
 <span data-ttu-id="72b9f-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="72b9f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b9f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="72b9f-116">See also</span></span>
- [<span data-ttu-id="72b9f-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="72b9f-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="72b9f-118">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="72b9f-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
