---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d28d0556a662099e4e5e74b22583fc3c8b4c313f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656108"
---
# <a name="-vbruntime"></a><span data-ttu-id="a8eb8-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="a8eb8-102">-vbruntime</span></span>
<span data-ttu-id="a8eb8-103">指定编译器应在不引用 Visual Basic 运行库的情况下进行编译，或在引用特定运行库的情况下进行编译。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8eb8-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8eb8-104">Syntax</span></span>  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="a8eb8-105">自变量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="a8eb8-106">编译而无需对 Visual Basic 运行时库的引用。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="a8eb8-107">使用默认的 Visual Basic 运行时库的引用进行编译。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="a8eb8-108">编译而不引用 Visual Basic 运行库，并将嵌入到程序集从 Visual Basic 运行库的核心功能。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="a8eb8-109">使用指定的库 (DLL) 的引用进行编译。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8eb8-110">备注</span><span class="sxs-lookup"><span data-stu-id="a8eb8-110">Remarks</span></span>  
 <span data-ttu-id="a8eb8-111">`-vbruntime`编译器选项，可指定编译器应编译而无需对 Visual Basic 运行时库的引用。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="a8eb8-112">如果编译而无需对 Visual Basic 运行时库的引用时，在生成的 Visual Basic 运行时帮助程序调用的代码或语言构造记录错误或警告。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="a8eb8-113">(A *Visual Basic 运行时帮助器*是在运行时执行特定的语言语义时调用的 Microsoft.VisualBasic.dll 中定义的函数。)</span><span class="sxs-lookup"><span data-stu-id="a8eb8-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="a8eb8-114">`-vbruntime+`选项生成相同的行为，如果没有则会发生`-vbruntime`指定开关。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="a8eb8-115">你可以使用`-vbruntime+`选项重写之前`-vbruntime`开关。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="a8eb8-116">大多数对象`My`使用时，类型将不可用`-vbruntime-`或`-vbruntime:path`选项。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="a8eb8-117">嵌入 Visual Basic 运行时核心功能</span><span class="sxs-lookup"><span data-stu-id="a8eb8-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="a8eb8-118">`-vbruntime*`选项使你能够对运行时库的引用的情况下编译。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="a8eb8-119">相反，从 Visual Basic 运行库的核心功能嵌入中用户程序集。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="a8eb8-120">如果在不包含 Visual Basic 运行时的平台上运行你的应用程序，你可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="a8eb8-121">嵌入以下运行时成员：</span><span class="sxs-lookup"><span data-stu-id="a8eb8-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="a8eb8-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> 类</span><span class="sxs-lookup"><span data-stu-id="a8eb8-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="a8eb8-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> 方法</span><span class="sxs-lookup"><span data-stu-id="a8eb8-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="a8eb8-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> 方法</span><span class="sxs-lookup"><span data-stu-id="a8eb8-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="a8eb8-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> 方法</span><span class="sxs-lookup"><span data-stu-id="a8eb8-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="a8eb8-126"><xref:Microsoft.VisualBasic.Constants.vbBack> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-127"><xref:Microsoft.VisualBasic.Constants.vbCr> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-130"><xref:Microsoft.VisualBasic.Constants.vbLf> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-134"><xref:Microsoft.VisualBasic.Constants.vbTab> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> 常量</span><span class="sxs-lookup"><span data-stu-id="a8eb8-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="a8eb8-136">某些对象`My`类型</span><span class="sxs-lookup"><span data-stu-id="a8eb8-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="a8eb8-137">如果在编译时使用`-vbruntime*`选项和你的代码从未嵌入的核心功能与 Visual Basic 运行时库引用的成员，编译器将返回错误，该值指示成员不可用。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="a8eb8-138">引用指定的库</span><span class="sxs-lookup"><span data-stu-id="a8eb8-138">Referencing a specified library</span></span>  
 <span data-ttu-id="a8eb8-139">你可以使用`path`自变量使用对自定义运行时库，而不是默认的 Visual Basic 运行时库的引用进行编译。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="a8eb8-140">如果值`path`参数为 DLL 的完全限定的路径，则编译器将使用该文件作为运行时库。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="a8eb8-141">如果值`path`参数不是 DLL 的完全限定的路径，Visual Basic 编译器将首先搜索当前文件夹中标识的 DLL。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="a8eb8-142">它然后将在使用指定的路径中搜索[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)编译器选项。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="a8eb8-143">如果`-sdkpath`不使用编译器选项，编译器将搜索在.NET Framework 文件夹中的标识 dll (`%systemroot%\Microsoft.NET\Framework\versionNumber`)。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8eb8-144">示例</span><span class="sxs-lookup"><span data-stu-id="a8eb8-144">Example</span></span>  
 <span data-ttu-id="a8eb8-145">下面的示例演示如何使用`-vbruntime`选项使用对自定义库的引用进行编译。</span><span class="sxs-lookup"><span data-stu-id="a8eb8-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8eb8-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8eb8-146">See Also</span></span>  
 [<span data-ttu-id="a8eb8-147">Visual Basic 核心 – 在 Visual Studio 2010 SP1 中的新编译模式</span><span class="sxs-lookup"><span data-stu-id="a8eb8-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [<span data-ttu-id="a8eb8-148">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="a8eb8-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a8eb8-149">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="a8eb8-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="a8eb8-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="a8eb8-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
