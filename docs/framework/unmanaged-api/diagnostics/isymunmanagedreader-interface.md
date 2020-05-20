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
ms.openlocfilehash: b372021fcda39d9973d96a9c39e93e38617887a6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615457"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="c7547-102">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="c7547-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="c7547-103">表示一个符号读取器，该读取器提供对符号存储区中的文档、方法和变量的访问。</span><span class="sxs-lookup"><span data-stu-id="c7547-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7547-104">方法</span><span class="sxs-lookup"><span data-stu-id="c7547-104">Methods</span></span>  
  
|<span data-ttu-id="c7547-105">方法</span><span class="sxs-lookup"><span data-stu-id="c7547-105">Method</span></span>|<span data-ttu-id="c7547-106">说明</span><span class="sxs-lookup"><span data-stu-id="c7547-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7547-107">GetDocument 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-107">GetDocument Method</span></span>](isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="c7547-108">查找文档。</span><span class="sxs-lookup"><span data-stu-id="c7547-108">Finds a document.</span></span>|  
|[<span data-ttu-id="c7547-109">GetDocuments 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-109">GetDocuments Method</span></span>](isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="c7547-110">返回在符号存储区中定义的所有文档的数组。</span><span class="sxs-lookup"><span data-stu-id="c7547-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="c7547-111">GetDocumentVersion 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-111">GetDocumentVersion Method</span></span>](isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="c7547-112">获取指定文档的指定版本。</span><span class="sxs-lookup"><span data-stu-id="c7547-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="c7547-113">GetGlobalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-113">GetGlobalVariables Method</span></span>](isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="c7547-114">返回所有全局变量。</span><span class="sxs-lookup"><span data-stu-id="c7547-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="c7547-115">GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-115">GetMethod Method</span></span>](isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="c7547-116">在给定方法标记的情况下，获取符号读取器方法。</span><span class="sxs-lookup"><span data-stu-id="c7547-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="c7547-117">GetMethodByVersion 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-117">GetMethodByVersion Method</span></span>](isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="c7547-118">在给定方法标记和编辑和复制版本号的情况下，获取符号读取器方法。</span><span class="sxs-lookup"><span data-stu-id="c7547-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="c7547-119">GetMethodFromDocumentPosition 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-119">GetMethodFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="c7547-120">返回包含文档中给定位置处的断点的方法。</span><span class="sxs-lookup"><span data-stu-id="c7547-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="c7547-121">GetMethodsFromDocumentPosition 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-121">GetMethodsFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="c7547-122">返回一组方法，其中每个方法都包含文档中给定位置处的断点。</span><span class="sxs-lookup"><span data-stu-id="c7547-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="c7547-123">GetMethodVersion 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-123">GetMethodVersion Method</span></span>](isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="c7547-124">获取方法版本。</span><span class="sxs-lookup"><span data-stu-id="c7547-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="c7547-125">GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-125">GetNamespaces Method</span></span>](isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="c7547-126">获取在此符号存储区的全局范围内定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c7547-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="c7547-127">GetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-127">GetSymAttribute Method</span></span>](isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="c7547-128">根据名称获取自定义属性。</span><span class="sxs-lookup"><span data-stu-id="c7547-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="c7547-129">GetSymbolStoreFileName 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-129">GetSymbolStoreFileName Method</span></span>](isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="c7547-130">提供符号存储区的磁盘上的文件名。</span><span class="sxs-lookup"><span data-stu-id="c7547-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="c7547-131">GetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-131">GetUserEntryPoint Method</span></span>](isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="c7547-132">返回指定为模块的用户入口点的方法（如果有）。</span><span class="sxs-lookup"><span data-stu-id="c7547-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="c7547-133">GetVariables 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-133">GetVariables Method</span></span>](isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="c7547-134">根据给定的父和名称返回非局部变量。</span><span class="sxs-lookup"><span data-stu-id="c7547-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="c7547-135">Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-135">Initialize Method</span></span>](isymunmanagedreader-initialize-method.md)|<span data-ttu-id="c7547-136">用此读取器将与之关联的元数据导入程序接口以及模块的文件名初始化符号读取器。</span><span class="sxs-lookup"><span data-stu-id="c7547-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="c7547-137">ReplaceSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-137">ReplaceSymbolStore Method</span></span>](isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="c7547-138">用增量符号存储区替换现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="c7547-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="c7547-139">UpdateSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="c7547-139">UpdateSymbolStore Method</span></span>](isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="c7547-140">使用增量符号存储区更新现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="c7547-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7547-141">要求</span><span class="sxs-lookup"><span data-stu-id="c7547-141">Requirements</span></span>  
 <span data-ttu-id="c7547-142">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="c7547-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7547-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7547-143">See also</span></span>

- [<span data-ttu-id="c7547-144">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="c7547-144">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c7547-145">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="c7547-145">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
