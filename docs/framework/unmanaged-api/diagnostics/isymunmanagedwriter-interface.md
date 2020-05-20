---
title: ISymUnmanagedWriter 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: 8f0bbd26bde562df5482d167c9d2775e01426f55
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610049"
---
# <a name="isymunmanagedwriter-interface"></a><span data-ttu-id="d797e-102">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="d797e-102">ISymUnmanagedWriter Interface</span></span>
<span data-ttu-id="d797e-103">表示符号编写器，并提供定义文档、序列点、词法范围和变量的方法。</span><span class="sxs-lookup"><span data-stu-id="d797e-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d797e-104">方法</span><span class="sxs-lookup"><span data-stu-id="d797e-104">Methods</span></span>  
  
|<span data-ttu-id="d797e-105">方法</span><span class="sxs-lookup"><span data-stu-id="d797e-105">Method</span></span>|<span data-ttu-id="d797e-106">说明</span><span class="sxs-lookup"><span data-stu-id="d797e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d797e-107">Abort 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-107">Abort Method</span></span>](isymunmanagedwriter-abort-method.md)|<span data-ttu-id="d797e-108">关闭符号编写器，而不将符号提交到符号存储区。</span><span class="sxs-lookup"><span data-stu-id="d797e-108">Closes the symbol writer without committing the symbols to the symbol store.</span></span>|  
|[<span data-ttu-id="d797e-109">Close 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-109">Close Method</span></span>](isymunmanagedwriter-close-method.md)|<span data-ttu-id="d797e-110">将符号提交到符号存储区后关闭符号编写器。</span><span class="sxs-lookup"><span data-stu-id="d797e-110">Closes the symbol writer after committing the symbols to the symbol store.</span></span>|  
|[<span data-ttu-id="d797e-111">CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-111">CloseMethod Method</span></span>](isymunmanagedwriter-closemethod-method.md)|<span data-ttu-id="d797e-112">关闭当前方法。</span><span class="sxs-lookup"><span data-stu-id="d797e-112">Closes the current method.</span></span> <span data-ttu-id="d797e-113">方法关闭后，不能在其中定义更多符号。</span><span class="sxs-lookup"><span data-stu-id="d797e-113">Once a method is closed, no more symbols can be defined within it.</span></span>|  
|[<span data-ttu-id="d797e-114">CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-114">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)|<span data-ttu-id="d797e-115">关闭最近打开的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d797e-115">Closes the most recently opened namespace.</span></span>|  
|[<span data-ttu-id="d797e-116">CloseScope 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-116">CloseScope Method</span></span>](isymunmanagedwriter-closescope-method.md)|<span data-ttu-id="d797e-117">关闭当前词法范围。</span><span class="sxs-lookup"><span data-stu-id="d797e-117">Closes the current lexical scope.</span></span>|  
|[<span data-ttu-id="d797e-118">DefineConstant 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-118">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)|<span data-ttu-id="d797e-119">定义常数值的名称。</span><span class="sxs-lookup"><span data-stu-id="d797e-119">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="d797e-120">DefineDocument 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-120">DefineDocument Method</span></span>](isymunmanagedwriter-definedocument-method.md)|<span data-ttu-id="d797e-121">定义源文档。</span><span class="sxs-lookup"><span data-stu-id="d797e-121">Defines a source document.</span></span>|  
|[<span data-ttu-id="d797e-122">DefineField 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-122">DefineField Method</span></span>](isymunmanagedwriter-definefield-method.md)|<span data-ttu-id="d797e-123">定义不在方法中的单个变量。</span><span class="sxs-lookup"><span data-stu-id="d797e-123">Defines a single variable that is not within a method.</span></span>|  
|[<span data-ttu-id="d797e-124">DefineGlobalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-124">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)|<span data-ttu-id="d797e-125">定义单个全局变量。</span><span class="sxs-lookup"><span data-stu-id="d797e-125">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="d797e-126">DefineLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-126">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)|<span data-ttu-id="d797e-127">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="d797e-127">Defines a single variable in the current lexical scope.</span></span>|  
|[<span data-ttu-id="d797e-128">DefineParameter 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-128">DefineParameter Method</span></span>](isymunmanagedwriter-defineparameter-method.md)|<span data-ttu-id="d797e-129">在当前方法中定义单个参数。</span><span class="sxs-lookup"><span data-stu-id="d797e-129">Defines a single parameter in the current method.</span></span>|  
|[<span data-ttu-id="d797e-130">DefineSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-130">DefineSequencePoints Method</span></span>](isymunmanagedwriter-definesequencepoints-method.md)|<span data-ttu-id="d797e-131">在当前方法内定义一组序列点。</span><span class="sxs-lookup"><span data-stu-id="d797e-131">Defines a group of sequence points within the current method.</span></span>|  
|[<span data-ttu-id="d797e-132">GetDebugInfo 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-132">GetDebugInfo Method</span></span>](isymunmanagedwriter-getdebuginfo-method.md)|<span data-ttu-id="d797e-133">返回编译器编写可移植可执行（PE）文件头中的调试目录条目所需的信息。</span><span class="sxs-lookup"><span data-stu-id="d797e-133">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span>|  
|[<span data-ttu-id="d797e-134">Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-134">Initialize Method</span></span>](isymunmanagedwriter-initialize-method.md)|<span data-ttu-id="d797e-135">设置此编写器将与之关联的元数据发射器接口，并设置调试符号将写入的输出文件名。</span><span class="sxs-lookup"><span data-stu-id="d797e-135">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>|  
|[<span data-ttu-id="d797e-136">Initialize2 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-136">Initialize2 Method</span></span>](isymunmanagedwriter-initialize2-method.md)|<span data-ttu-id="d797e-137">设置此编写器将与之关联的元数据发射器接口，设置调试符号将写入的输出文件名，并设置程序数据库（PDB）文件的最终位置。</span><span class="sxs-lookup"><span data-stu-id="d797e-137">Sets the metadata emitter interface with which this writer will be associated, sets the output file name to which the debugging symbols will be written, and sets the final location of the program database (PDB) file.</span></span>|  
|[<span data-ttu-id="d797e-138">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-138">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)|<span data-ttu-id="d797e-139">打开要在其中发出符号信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d797e-139">Opens a method into which symbol information is emitted.</span></span>|  
|[<span data-ttu-id="d797e-140">OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-140">OpenNamespace Method</span></span>](isymunmanagedwriter-opennamespace-method.md)|<span data-ttu-id="d797e-141">打开一个新的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d797e-141">Opens a new namespace.</span></span>|  
|[<span data-ttu-id="d797e-142">OpenScope 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-142">OpenScope Method</span></span>](isymunmanagedwriter-openscope-method.md)|<span data-ttu-id="d797e-143">在当前方法中打开新的词法范围。</span><span class="sxs-lookup"><span data-stu-id="d797e-143">Opens a new lexical scope in the current method.</span></span>|  
|[<span data-ttu-id="d797e-144">RemapToken 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-144">RemapToken Method</span></span>](isymunmanagedwriter-remaptoken-method.md)|<span data-ttu-id="d797e-145">通知符号编写器在发出元数据时已重新映射元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d797e-145">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span>|  
|[<span data-ttu-id="d797e-146">SetMethodSourceRange 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-146">SetMethodSourceRange Method</span></span>](isymunmanagedwriter-setmethodsourcerange-method.md)|<span data-ttu-id="d797e-147">指定源文件内方法的真正开始和结尾。</span><span class="sxs-lookup"><span data-stu-id="d797e-147">Specifies the true start and end of a method within a source file.</span></span>|  
|[<span data-ttu-id="d797e-148">SetScopeRange 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-148">SetScopeRange Method</span></span>](isymunmanagedwriter-setscoperange-method.md)|<span data-ttu-id="d797e-149">定义指定词法范围的偏移量范围。</span><span class="sxs-lookup"><span data-stu-id="d797e-149">Defines the offset range for the specified lexical scope.</span></span>|  
|[<span data-ttu-id="d797e-150">SetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-150">SetSymAttribute Method</span></span>](isymunmanagedwriter-setsymattribute-method.md)|<span data-ttu-id="d797e-151">基于名称定义自定义属性。</span><span class="sxs-lookup"><span data-stu-id="d797e-151">Defines a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="d797e-152">SetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-152">SetUserEntryPoint Method</span></span>](isymunmanagedwriter-setuserentrypoint-method.md)|<span data-ttu-id="d797e-153">指定用户定义的方法，该方法是此模块的入口点。</span><span class="sxs-lookup"><span data-stu-id="d797e-153">Specifies the user-defined method that is the entry point for this module.</span></span>|  
|[<span data-ttu-id="d797e-154">UsingNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="d797e-154">UsingNamespace Method</span></span>](isymunmanagedwriter-usingnamespace-method.md)|<span data-ttu-id="d797e-155">指定在当前打开的词法范围内使用给定的完全限定的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="d797e-155">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d797e-156">要求</span><span class="sxs-lookup"><span data-stu-id="d797e-156">Requirements</span></span>  
 <span data-ttu-id="d797e-157">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="d797e-157">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d797e-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d797e-158">See also</span></span>

- [<span data-ttu-id="d797e-159">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="d797e-159">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d797e-160">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="d797e-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="d797e-161">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="d797e-161">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
