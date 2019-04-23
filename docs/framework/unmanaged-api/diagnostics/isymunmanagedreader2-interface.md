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
ms.openlocfilehash: 890053e1bf2e0648a41cca718e94edcf21c7e612
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165979"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="949c6-102">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="949c6-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="949c6-103">表示提供对文档、 方法和符号存储区中的变量的访问的符号读取器。</span><span class="sxs-lookup"><span data-stu-id="949c6-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="949c6-104">此接口扩展[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="949c6-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="949c6-105">方法</span><span class="sxs-lookup"><span data-stu-id="949c6-105">Methods</span></span>  
  
|<span data-ttu-id="949c6-106">方法</span><span class="sxs-lookup"><span data-stu-id="949c6-106">Method</span></span>|<span data-ttu-id="949c6-107">描述</span><span class="sxs-lookup"><span data-stu-id="949c6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="949c6-108">GetMethodByVersionPreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="949c6-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="949c6-109">获取符号读取器方法，给定一个方法标记和编辑并继续的版本号。</span><span class="sxs-lookup"><span data-stu-id="949c6-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="949c6-110">GetMethodsInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="949c6-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="949c6-111">获取每个方法中提供的文档包含行信息。</span><span class="sxs-lookup"><span data-stu-id="949c6-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="949c6-112">GetSymAttributePreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="949c6-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="949c6-113">获取根据其名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="949c6-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="949c6-114">要求</span><span class="sxs-lookup"><span data-stu-id="949c6-114">Requirements</span></span>  
 <span data-ttu-id="949c6-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="949c6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="949c6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="949c6-116">See also</span></span>

- [<span data-ttu-id="949c6-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="949c6-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="949c6-118">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="949c6-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
