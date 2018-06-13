---
title: ISymUnmanagedReader 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a78616ea1dccdf82c4e00d23d2ff630c98cb4e38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431898"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="3dc87-102">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="3dc87-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="3dc87-103">表示提供对文档、 方法和符号存储区内的变量的访问的符号读取器。</span><span class="sxs-lookup"><span data-stu-id="3dc87-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3dc87-104">方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-104">Methods</span></span>  
  
|<span data-ttu-id="3dc87-105">方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-105">Method</span></span>|<span data-ttu-id="3dc87-106">描述</span><span class="sxs-lookup"><span data-stu-id="3dc87-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3dc87-107">GetDocument 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="3dc87-108">查找文档。</span><span class="sxs-lookup"><span data-stu-id="3dc87-108">Finds a document.</span></span>|  
|[<span data-ttu-id="3dc87-109">GetDocuments 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="3dc87-110">返回在符号存储区中定义的所有文档的数组。</span><span class="sxs-lookup"><span data-stu-id="3dc87-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="3dc87-111">GetDocumentVersion 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="3dc87-112">获取指定的文档的指定的版本。</span><span class="sxs-lookup"><span data-stu-id="3dc87-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="3dc87-113">GetGlobalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="3dc87-114">返回所有全局变量。</span><span class="sxs-lookup"><span data-stu-id="3dc87-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="3dc87-115">GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="3dc87-116">获取符号读取器方法，给定一个方法标记。</span><span class="sxs-lookup"><span data-stu-id="3dc87-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="3dc87-117">GetMethodByVersion 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="3dc87-118">获取符号读取器方法，在给定方法标记和编辑复制版本号。</span><span class="sxs-lookup"><span data-stu-id="3dc87-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="3dc87-119">GetMethodFromDocumentPosition 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="3dc87-120">返回包含在文档中的给定位置处的断点的方法。</span><span class="sxs-lookup"><span data-stu-id="3dc87-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="3dc87-121">GetMethodsFromDocumentPosition 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="3dc87-122">返回的数组的方法，其中每个包含文档中的给定位置处的断点。</span><span class="sxs-lookup"><span data-stu-id="3dc87-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="3dc87-123">GetMethodVersion 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="3dc87-124">获取的方法版本。</span><span class="sxs-lookup"><span data-stu-id="3dc87-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="3dc87-125">GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="3dc87-126">获取在此符号存储区中的全局范围内定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3dc87-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="3dc87-127">GetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="3dc87-128">获取基于其名称的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="3dc87-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="3dc87-129">GetSymbolStoreFileName 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="3dc87-130">提供符号存储区的磁盘上的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3dc87-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="3dc87-131">GetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="3dc87-132">如果有，则返回指定为该模块的用户入口点的方法。</span><span class="sxs-lookup"><span data-stu-id="3dc87-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="3dc87-133">GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="3dc87-134">返回一个非本地变量，给定的父级和名称。</span><span class="sxs-lookup"><span data-stu-id="3dc87-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="3dc87-135">Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="3dc87-136">初始化此读取器将与，以及该模块的文件名称相关联的元数据导入程序接口的符号读取器。</span><span class="sxs-lookup"><span data-stu-id="3dc87-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="3dc87-137">ReplaceSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="3dc87-138">用增量符号存储区替换现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="3dc87-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="3dc87-139">UpdateSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="3dc87-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="3dc87-140">使用增量符号存储区更新现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="3dc87-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3dc87-141">要求</span><span class="sxs-lookup"><span data-stu-id="3dc87-141">Requirements</span></span>  
 <span data-ttu-id="3dc87-142">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3dc87-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dc87-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dc87-143">See Also</span></span>  
 [<span data-ttu-id="3dc87-144">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="3dc87-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="3dc87-145">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="3dc87-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
