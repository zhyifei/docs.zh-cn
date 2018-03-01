---
title: "ISymUnmanagedWriter 接口"
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
- ISymUnmanagedWriter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter
helpviewer_keywords:
- ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f4996f0196df4c2bcf890df6ad972f313403e435
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter-interface"></a><span data-ttu-id="67d91-102">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="67d91-102">ISymUnmanagedWriter Interface</span></span>
<span data-ttu-id="67d91-103">表示符号编写器，并提供方法来定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="67d91-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67d91-104">方法</span><span class="sxs-lookup"><span data-stu-id="67d91-104">Methods</span></span>  
  
|<span data-ttu-id="67d91-105">方法</span><span class="sxs-lookup"><span data-stu-id="67d91-105">Method</span></span>|<span data-ttu-id="67d91-106">描述</span><span class="sxs-lookup"><span data-stu-id="67d91-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67d91-107">Abort 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-107">Abort Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|<span data-ttu-id="67d91-108">关闭而不将符号提交到符号存储区的符号编写器。</span><span class="sxs-lookup"><span data-stu-id="67d91-108">Closes the symbol writer without committing the symbols to the symbol store.</span></span>|  
|[<span data-ttu-id="67d91-109">Close 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-109">Close Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|<span data-ttu-id="67d91-110">将符号提交到符号存储区后关闭符号编写器。</span><span class="sxs-lookup"><span data-stu-id="67d91-110">Closes the symbol writer after committing the symbols to the symbol store.</span></span>|  
|[<span data-ttu-id="67d91-111">CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-111">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|<span data-ttu-id="67d91-112">关闭当前方法。</span><span class="sxs-lookup"><span data-stu-id="67d91-112">Closes the current method.</span></span> <span data-ttu-id="67d91-113">一旦关闭方法，可以在其中定义没有更多的符号。</span><span class="sxs-lookup"><span data-stu-id="67d91-113">Once a method is closed, no more symbols can be defined within it.</span></span>|  
|[<span data-ttu-id="67d91-114">CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-114">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|<span data-ttu-id="67d91-115">关闭最近打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="67d91-115">Closes the most recently opened namespace.</span></span>|  
|[<span data-ttu-id="67d91-116">CloseScope 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-116">CloseScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|<span data-ttu-id="67d91-117">关闭当前词法范围。</span><span class="sxs-lookup"><span data-stu-id="67d91-117">Closes the current lexical scope.</span></span>|  
|[<span data-ttu-id="67d91-118">DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-118">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|<span data-ttu-id="67d91-119">定义的常量值的名称。</span><span class="sxs-lookup"><span data-stu-id="67d91-119">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="67d91-120">DefineDocument 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-120">DefineDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|<span data-ttu-id="67d91-121">定义源文档。</span><span class="sxs-lookup"><span data-stu-id="67d91-121">Defines a source document.</span></span>|  
|[<span data-ttu-id="67d91-122">DefineField 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-122">DefineField Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|<span data-ttu-id="67d91-123">定义一个不在方法内的变量。</span><span class="sxs-lookup"><span data-stu-id="67d91-123">Defines a single variable that is not within a method.</span></span>|  
|[<span data-ttu-id="67d91-124">DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-124">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|<span data-ttu-id="67d91-125">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="67d91-125">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="67d91-126">DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-126">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|<span data-ttu-id="67d91-127">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="67d91-127">Defines a single variable in the current lexical scope.</span></span>|  
|[<span data-ttu-id="67d91-128">DefineParameter 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-128">DefineParameter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|<span data-ttu-id="67d91-129">在当前方法中定义的单个参数。</span><span class="sxs-lookup"><span data-stu-id="67d91-129">Defines a single parameter in the current method.</span></span>|  
|[<span data-ttu-id="67d91-130">DefineSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-130">DefineSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|<span data-ttu-id="67d91-131">在当前方法内定义一组序列点。</span><span class="sxs-lookup"><span data-stu-id="67d91-131">Defines a group of sequence points within the current method.</span></span>|  
|[<span data-ttu-id="67d91-132">GetDebugInfo 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-132">GetDebugInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|<span data-ttu-id="67d91-133">返回编译器编写可移植可执行 (PE) 文件头中的调试目录项所需的信息。</span><span class="sxs-lookup"><span data-stu-id="67d91-133">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span>|  
|[<span data-ttu-id="67d91-134">Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-134">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|<span data-ttu-id="67d91-135">设置元数据发射器接口此编写器将与之相关联，并设置将向其写入调试符号的输出文件名称。</span><span class="sxs-lookup"><span data-stu-id="67d91-135">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>|  
|[<span data-ttu-id="67d91-136">Initialize2 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-136">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|<span data-ttu-id="67d91-137">设置此编写器将与之关联的元数据发射器接口，设置输出文件的名称向其调试符号将写入和设置的程序数据库 (PDB) 文件的最终位置。</span><span class="sxs-lookup"><span data-stu-id="67d91-137">Sets the metadata emitter interface with which this writer will be associated, sets the output file name to which the debugging symbols will be written, and sets the final location of the program database (PDB) file.</span></span>|  
|[<span data-ttu-id="67d91-138">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-138">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|<span data-ttu-id="67d91-139">打开一个到哪些符号发出信息的方法。</span><span class="sxs-lookup"><span data-stu-id="67d91-139">Opens a method into which symbol information is emitted.</span></span>|  
|[<span data-ttu-id="67d91-140">OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-140">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|<span data-ttu-id="67d91-141">打开一个新的命名空间。</span><span class="sxs-lookup"><span data-stu-id="67d91-141">Opens a new namespace.</span></span>|  
|[<span data-ttu-id="67d91-142">OpenScope 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-142">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|<span data-ttu-id="67d91-143">在当前方法中打开新的词法范围。</span><span class="sxs-lookup"><span data-stu-id="67d91-143">Opens a new lexical scope in the current method.</span></span>|  
|[<span data-ttu-id="67d91-144">RemapToken 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-144">RemapToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|<span data-ttu-id="67d91-145">通知符号编写器元数据标记在发出元数据已被重新映射。</span><span class="sxs-lookup"><span data-stu-id="67d91-145">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span>|  
|[<span data-ttu-id="67d91-146">SetMethodSourceRange 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-146">SetMethodSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|<span data-ttu-id="67d91-147">指定的真正开始和结束源文件中的方法。</span><span class="sxs-lookup"><span data-stu-id="67d91-147">Specifies the true start and end of a method within a source file.</span></span>|  
|[<span data-ttu-id="67d91-148">SetScopeRange 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-148">SetScopeRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|<span data-ttu-id="67d91-149">定义指定词法范围的偏移量范围。</span><span class="sxs-lookup"><span data-stu-id="67d91-149">Defines the offset range for the specified lexical scope.</span></span>|  
|[<span data-ttu-id="67d91-150">SetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-150">SetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|<span data-ttu-id="67d91-151">定义基于其名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="67d91-151">Defines a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="67d91-152">SetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-152">SetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|<span data-ttu-id="67d91-153">指定是为此模块的入口点的用户定义的方法。</span><span class="sxs-lookup"><span data-stu-id="67d91-153">Specifies the user-defined method that is the entry point for this module.</span></span>|  
|[<span data-ttu-id="67d91-154">UsingNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="67d91-154">UsingNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|<span data-ttu-id="67d91-155">指定当前打开的词法范围内，使用给定的完全限定的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="67d91-155">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67d91-156">惠?</span><span class="sxs-lookup"><span data-stu-id="67d91-156">Requirements</span></span>  
 <span data-ttu-id="67d91-157">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="67d91-157">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d91-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="67d91-158">See Also</span></span>  
 [<span data-ttu-id="67d91-159">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="67d91-159">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="67d91-160">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="67d91-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="67d91-161">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="67d91-161">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
