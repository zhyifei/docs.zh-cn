---
title: 诊断符号存储区接口
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
ms.openlocfilehash: bdb691570a9a2bf7bd2bb21af500b06c10b0bc53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448521"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="06b6f-102">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="06b6f-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span><span class="sxs-lookup"><span data-stu-id="06b6f-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06b6f-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="06b6f-104">In This Section</span></span>  
 [<span data-ttu-id="06b6f-105">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="06b6f-106">Provides methods that display current binding information about the running application.</span><span class="sxs-lookup"><span data-stu-id="06b6f-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="06b6f-107">IDebugAutoAttach 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="06b6f-108">Defines the interface for a server-invoked debugger auto attach.</span><span class="sxs-lookup"><span data-stu-id="06b6f-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="06b6f-109">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="06b6f-110">Declares methods for registering and unregistering a connection notification source.</span><span class="sxs-lookup"><span data-stu-id="06b6f-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="06b6f-111">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="06b6f-112">Declares methods for sink notification.</span><span class="sxs-lookup"><span data-stu-id="06b6f-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="06b6f-113">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="06b6f-114">Declares a method for setting notification filters.</span><span class="sxs-lookup"><span data-stu-id="06b6f-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="06b6f-115">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="06b6f-116">Provides information for the Edit and Continue feature.</span><span class="sxs-lookup"><span data-stu-id="06b6f-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="06b6f-117">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="06b6f-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="06b6f-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="06b6f-119">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="06b6f-120">Allows definition of optional async method information per method symbol.</span><span class="sxs-lookup"><span data-stu-id="06b6f-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="06b6f-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="06b6f-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="06b6f-122">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="06b6f-123">Represents a symbol binder for unmanaged code.</span><span class="sxs-lookup"><span data-stu-id="06b6f-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="06b6f-124">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="06b6f-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="06b6f-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="06b6f-126">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="06b6f-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="06b6f-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="06b6f-128">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="06b6f-129">Provides access to unmanaged constants.</span><span class="sxs-lookup"><span data-stu-id="06b6f-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="06b6f-130">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="06b6f-131">Disposes of unmanaged resources.</span><span class="sxs-lookup"><span data-stu-id="06b6f-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="06b6f-132">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="06b6f-133">表示由符号存储引用的文档。</span><span class="sxs-lookup"><span data-stu-id="06b6f-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="06b6f-134">ISymUnmanagedDocumentWriter 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="06b6f-135">提供用于写入到符号存储区引用的文档的方法。</span><span class="sxs-lookup"><span data-stu-id="06b6f-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="06b6f-136">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="06b6f-137">Provides methods for the Edit and Continue feature.</span><span class="sxs-lookup"><span data-stu-id="06b6f-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="06b6f-138">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="06b6f-139">Represents a method within the symbol store.</span><span class="sxs-lookup"><span data-stu-id="06b6f-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="06b6f-140">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="06b6f-141">Represents a namespace.</span><span class="sxs-lookup"><span data-stu-id="06b6f-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="06b6f-142">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="06b6f-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span><span class="sxs-lookup"><span data-stu-id="06b6f-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="06b6f-144">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="06b6f-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span><span class="sxs-lookup"><span data-stu-id="06b6f-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="06b6f-146">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="06b6f-147">Provides methods that get symbol search information.</span><span class="sxs-lookup"><span data-stu-id="06b6f-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="06b6f-148">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="06b6f-149">Represents a lexical scope within a method.</span><span class="sxs-lookup"><span data-stu-id="06b6f-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="06b6f-150">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="06b6f-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span><span class="sxs-lookup"><span data-stu-id="06b6f-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="06b6f-152">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="06b6f-153">Provides source server data for a module.</span><span class="sxs-lookup"><span data-stu-id="06b6f-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="06b6f-154">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="06b6f-155">Provides methods that get information about the search path.</span><span class="sxs-lookup"><span data-stu-id="06b6f-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="06b6f-156">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="06b6f-157">Represents a variable, such as a parameter, a local variable, or a field.</span><span class="sxs-lookup"><span data-stu-id="06b6f-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="06b6f-158">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="06b6f-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="06b6f-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="06b6f-160">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="06b6f-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="06b6f-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="06b6f-162">Extends the `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="06b6f-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="06b6f-163">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="06b6f-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="06b6f-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="06b6f-165">Extends the `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="06b6f-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="06b6f-166">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="06b6f-167">ISymUnmanagedWriter4 interface.</span><span class="sxs-lookup"><span data-stu-id="06b6f-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="06b6f-168">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="06b6f-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="06b6f-169">ISymUnmanagedWriter5 interface.</span><span class="sxs-lookup"><span data-stu-id="06b6f-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="06b6f-170">相关章节</span><span class="sxs-lookup"><span data-stu-id="06b6f-170">Related Sections</span></span>  
 [<span data-ttu-id="06b6f-171">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="06b6f-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="06b6f-172">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="06b6f-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="06b6f-173">调试</span><span class="sxs-lookup"><span data-stu-id="06b6f-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
