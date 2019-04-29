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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fca7359888b8b73b2e1cf709ab708d71abf0db6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787889"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="6e701-102">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="6e701-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="6e701-103">本主题介绍启用编译器以生成由调试器使用的符号信息的非托管的接口。</span><span class="sxs-lookup"><span data-stu-id="6e701-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e701-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="6e701-104">In This Section</span></span>  
 [<span data-ttu-id="6e701-105">IBindingDisplay 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="6e701-106">提供显示当前运行的应用程序有关的绑定信息的方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="6e701-107">IDebugAutoAttach 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="6e701-108">服务器调用调试器自动连接定义的接口。</span><span class="sxs-lookup"><span data-stu-id="6e701-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="6e701-109">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="6e701-110">声明用于注册和注销连接通知源的方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="6e701-111">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="6e701-112">声明用于接收器通知的方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="6e701-113">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="6e701-114">声明设置通知筛选器的方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="6e701-115">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="6e701-116">提供有关编辑并继续功能的信息。</span><span class="sxs-lookup"><span data-stu-id="6e701-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="6e701-117">ISymUnmanagedAsyncMethod 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="6e701-118">此接口是对的阅读补充[ISymUnmanagedAsyncMethodPropertiesWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="6e701-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="6e701-119">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="6e701-120">允许定义每个方法符号的可选的异步方法信息。</span><span class="sxs-lookup"><span data-stu-id="6e701-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="6e701-121">必须使用与打开方法 (即，调用之间[OpenMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)并[CloseMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md))。</span><span class="sxs-lookup"><span data-stu-id="6e701-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="6e701-122">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="6e701-123">表示非托管代码的符号联编程序。</span><span class="sxs-lookup"><span data-stu-id="6e701-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="6e701-124">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="6e701-125">表示非托管代码的符号联编程序和扩展`ISymUnmanagedBinder`接口。</span><span class="sxs-lookup"><span data-stu-id="6e701-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="6e701-126">ISymUnmanagedBinder3 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="6e701-127">表示非托管代码的符号联编程序和扩展`ISymUnmanagedBinder`接口。</span><span class="sxs-lookup"><span data-stu-id="6e701-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="6e701-128">ISymUnmanagedConstant 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="6e701-129">提供对非托管的常量的访问。</span><span class="sxs-lookup"><span data-stu-id="6e701-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="6e701-130">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="6e701-131">释放非托管资源。</span><span class="sxs-lookup"><span data-stu-id="6e701-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="6e701-132">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="6e701-133">表示由符号存储引用的文档。</span><span class="sxs-lookup"><span data-stu-id="6e701-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="6e701-134">ISymUnmanagedDocumentWriter 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="6e701-135">提供用于写入到符号存储区引用的文档的方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="6e701-136">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="6e701-137">提供有关编辑并继续功能的方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="6e701-138">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="6e701-139">表示符号存储区中的一个方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="6e701-140">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="6e701-141">表示一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="6e701-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="6e701-142">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="6e701-143">表示提供对文档、 方法和符号存储区中的变量的访问的符号读取器。</span><span class="sxs-lookup"><span data-stu-id="6e701-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="6e701-144">ISymUnmanagedReader2 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="6e701-145">获取给定方法标记和编辑复制版本号的符号读取器方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="6e701-146">ISymUnmanagedReaderSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="6e701-147">提供用于获取符号搜索信息的方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="6e701-148">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="6e701-149">表示一种方法内的词法范围。</span><span class="sxs-lookup"><span data-stu-id="6e701-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="6e701-150">ISymUnmanagedScope2 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="6e701-151">表示在方法中，词法范围并扩展`ISymUnmanagedScope`接口使用的范围内获取有关定义的常量的信息的方法...</span><span class="sxs-lookup"><span data-stu-id="6e701-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="6e701-152">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="6e701-153">提供源服务器数据的模块。</span><span class="sxs-lookup"><span data-stu-id="6e701-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="6e701-154">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="6e701-155">提供了获取有关搜索路径的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="6e701-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="6e701-156">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="6e701-157">表示一个变量，例如参数、 局部变量或字段。</span><span class="sxs-lookup"><span data-stu-id="6e701-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="6e701-158">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="6e701-159">表示符号编写器，并提供方法用于定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="6e701-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="6e701-160">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="6e701-161">表示符号编写器，并提供方法用于定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="6e701-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="6e701-162">扩展了`ISymUnmanagedWriter`接口。</span><span class="sxs-lookup"><span data-stu-id="6e701-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="6e701-163">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="6e701-164">表示符号编写器，并提供方法用于定义文档、 序列点、 词法作用域和变量。</span><span class="sxs-lookup"><span data-stu-id="6e701-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="6e701-165">扩展了`ISymUnmanagedWriter`接口。</span><span class="sxs-lookup"><span data-stu-id="6e701-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="6e701-166">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="6e701-167">ISymUnmanagedWriter4 接口。</span><span class="sxs-lookup"><span data-stu-id="6e701-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="6e701-168">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="6e701-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="6e701-169">ISymUnmanagedWriter5 接口。</span><span class="sxs-lookup"><span data-stu-id="6e701-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6e701-170">相关章节</span><span class="sxs-lookup"><span data-stu-id="6e701-170">Related Sections</span></span>  
 [<span data-ttu-id="6e701-171">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="6e701-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="6e701-172">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="6e701-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="6e701-173">调试</span><span class="sxs-lookup"><span data-stu-id="6e701-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
