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
ms.openlocfilehash: a07c75e14244fb5bdf72ff2b0d344ae27672ef89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448263"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="e693e-102">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="e693e-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="e693e-103">表示一个符号读取器，该读取器提供对符号存储区中的文档、方法和变量的访问。</span><span class="sxs-lookup"><span data-stu-id="e693e-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="e693e-104">此接口扩展[ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e693e-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e693e-105">方法</span><span class="sxs-lookup"><span data-stu-id="e693e-105">Methods</span></span>  
  
|<span data-ttu-id="e693e-106">方法</span><span class="sxs-lookup"><span data-stu-id="e693e-106">Method</span></span>|<span data-ttu-id="e693e-107">说明</span><span class="sxs-lookup"><span data-stu-id="e693e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e693e-108">GetMethodByVersionPreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="e693e-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="e693e-109">在给定方法标记和编辑并继续版本号的情况下，获取符号读取器方法。</span><span class="sxs-lookup"><span data-stu-id="e693e-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="e693e-110">GetMethodsInDocument 方法</span><span class="sxs-lookup"><span data-stu-id="e693e-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="e693e-111">获取所提供文档中包含行信息的每个方法。</span><span class="sxs-lookup"><span data-stu-id="e693e-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="e693e-112">GetSymAttributePreRemap 方法</span><span class="sxs-lookup"><span data-stu-id="e693e-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="e693e-113">根据名称获取自定义属性。</span><span class="sxs-lookup"><span data-stu-id="e693e-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e693e-114">要求</span><span class="sxs-lookup"><span data-stu-id="e693e-114">Requirements</span></span>  
 <span data-ttu-id="e693e-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="e693e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e693e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e693e-116">See also</span></span>

- [<span data-ttu-id="e693e-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="e693e-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e693e-118">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="e693e-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
