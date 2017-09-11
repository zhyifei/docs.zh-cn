---
title: "/vbruntime |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
dev_langs:
- VB
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cb07ed8c2f6070079cc51c290ff5a61305c5a5d3
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="vbruntime"></a><span data-ttu-id="3814f-102">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="3814f-102">/vbruntime</span></span>
<span data-ttu-id="3814f-103">指定编译器应在不引用 Visual Basic 运行库的情况下进行编译，或在引用特定运行库的情况下进行编译。</span><span class="sxs-lookup"><span data-stu-id="3814f-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3814f-104">语法</span><span class="sxs-lookup"><span data-stu-id="3814f-104">Syntax</span></span>  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="3814f-105">参数</span><span class="sxs-lookup"><span data-stu-id="3814f-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="3814f-106">编译而无需对 Visual Basic 运行库的引用。</span><span class="sxs-lookup"><span data-stu-id="3814f-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="3814f-107">为 Visual Basic 运行库的默认值的引用来编译。</span><span class="sxs-lookup"><span data-stu-id="3814f-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="3814f-108">对 Visual Basic 运行时库的引用的情况下编译，并将嵌入到程序集从 Visual Basic 运行库的核心功能。</span><span class="sxs-lookup"><span data-stu-id="3814f-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="3814f-109">对指定库 (DLL) 的引用来编译。</span><span class="sxs-lookup"><span data-stu-id="3814f-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3814f-110">备注</span><span class="sxs-lookup"><span data-stu-id="3814f-110">Remarks</span></span>  
 <span data-ttu-id="3814f-111">`/vbruntime`编译器选项可用于指定编译器应编译而无需对 Visual Basic 运行库的引用。</span><span class="sxs-lookup"><span data-stu-id="3814f-111">The `/vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="3814f-112">如果您对 Visual Basic 运行库的引用的情况下编译，错误或警告登录生成对 Visual Basic 运行时帮助器调用的代码或语言构造。</span><span class="sxs-lookup"><span data-stu-id="3814f-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="3814f-113">(A *Visual Basic 运行时帮助器*是在运行时执行特定的语言语义时调用的 Microsoft.VisualBasic.dll 中定义的函数。)</span><span class="sxs-lookup"><span data-stu-id="3814f-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="3814f-114">`/vbruntime+`选项将生成相同的行为，如果没有则会发生`/vbruntime`指定开关。</span><span class="sxs-lookup"><span data-stu-id="3814f-114">The `/vbruntime+` option produces the same behavior that occurs if no `/vbruntime` switch is specified.</span></span> <span data-ttu-id="3814f-115">您可以使用`/vbruntime+`选项重写之前`/vbruntime`开关。</span><span class="sxs-lookup"><span data-stu-id="3814f-115">You can use the `/vbruntime+` option to override previous `/vbruntime` switches.</span></span>  
  
 <span data-ttu-id="3814f-116">大多数对象的`My`使用时，类型将不可用`/vbruntime-`或`vbruntime:``path`选项。</span><span class="sxs-lookup"><span data-stu-id="3814f-116">Most objects of the `My` type are unavailable when you use the `/vbruntime-` or `vbruntime:``path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="3814f-117">嵌入 Visual Basic 运行时的核心功能</span><span class="sxs-lookup"><span data-stu-id="3814f-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="3814f-118">`/vbruntime*`选项使您能够对运行时库的引用的情况下编译。</span><span class="sxs-lookup"><span data-stu-id="3814f-118">The `/vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="3814f-119">相反，从 Visual Basic 运行库的核心功能嵌入用户程序集。</span><span class="sxs-lookup"><span data-stu-id="3814f-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="3814f-120">如果在不包含 Visual Basic 运行时的平台上运行你的应用程序，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="3814f-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="3814f-121">嵌入以下的运行库成员︰</span><span class="sxs-lookup"><span data-stu-id="3814f-121">The following runtime members are embedded:</span></span>  
  
-   <span data-ttu-id="3814f-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions>类</xref:Microsoft.VisualBasic.CompilerServices.Conversions></span><span class="sxs-lookup"><span data-stu-id="3814f-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
-   <span data-ttu-id="3814f-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>方法</xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29></span><span class="sxs-lookup"><span data-stu-id="3814f-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
-   <span data-ttu-id="3814f-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>方法</xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="3814f-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
-   <span data-ttu-id="3814f-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>方法</xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29></span><span class="sxs-lookup"><span data-stu-id="3814f-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
-   <span data-ttu-id="3814f-126"><xref:Microsoft.VisualBasic.Constants.vbBack>常量</xref:Microsoft.VisualBasic.Constants.vbBack></span><span class="sxs-lookup"><span data-stu-id="3814f-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
-   <span data-ttu-id="3814f-127"><xref:Microsoft.VisualBasic.Constants.vbCr>常量</xref:Microsoft.VisualBasic.Constants.vbCr></span><span class="sxs-lookup"><span data-stu-id="3814f-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
-   <span data-ttu-id="3814f-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf>常量</xref:Microsoft.VisualBasic.Constants.vbCrLf></span><span class="sxs-lookup"><span data-stu-id="3814f-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
-   <span data-ttu-id="3814f-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed>常量</xref:Microsoft.VisualBasic.Constants.vbFormFeed></span><span class="sxs-lookup"><span data-stu-id="3814f-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
-   <span data-ttu-id="3814f-130"><xref:Microsoft.VisualBasic.Constants.vbLf>常量</xref:Microsoft.VisualBasic.Constants.vbLf></span><span class="sxs-lookup"><span data-stu-id="3814f-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
-   <span data-ttu-id="3814f-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine>常量</xref:Microsoft.VisualBasic.Constants.vbNewLine></span><span class="sxs-lookup"><span data-stu-id="3814f-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
-   <span data-ttu-id="3814f-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar>常量</xref:Microsoft.VisualBasic.Constants.vbNullChar></span><span class="sxs-lookup"><span data-stu-id="3814f-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
-   <span data-ttu-id="3814f-133"><xref:Microsoft.VisualBasic.Constants.vbNullString>常量</xref:Microsoft.VisualBasic.Constants.vbNullString></span><span class="sxs-lookup"><span data-stu-id="3814f-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
-   <span data-ttu-id="3814f-134"><xref:Microsoft.VisualBasic.Constants.vbTab>常量</xref:Microsoft.VisualBasic.Constants.vbTab></span><span class="sxs-lookup"><span data-stu-id="3814f-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
-   <span data-ttu-id="3814f-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab>常量</xref:Microsoft.VisualBasic.Constants.vbVerticalTab></span><span class="sxs-lookup"><span data-stu-id="3814f-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
-   <span data-ttu-id="3814f-136">某些对象`My`类型</span><span class="sxs-lookup"><span data-stu-id="3814f-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="3814f-137">如果在编译时使用`/vbruntime*`选项和您的代码引用的成员没有嵌入的核心功能的 Visual Basic 运行时库中，编译器将返回一个错误，指示该成员不可用。</span><span class="sxs-lookup"><span data-stu-id="3814f-137">If you compile using the `/vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="3814f-138">引用指定的库</span><span class="sxs-lookup"><span data-stu-id="3814f-138">Referencing a specified library</span></span>  
 <span data-ttu-id="3814f-139">您可以使用`path`参数来编译到自定义运行时库而不是默认 Visual Basic 运行库的引用。</span><span class="sxs-lookup"><span data-stu-id="3814f-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="3814f-140">如果值为`path`参数是 DLL 的完全限定的路径，则编译器将使用该文件作为运行时库。</span><span class="sxs-lookup"><span data-stu-id="3814f-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="3814f-141">如果值为`path`参数不是对 DLL 的完全限定的路径、 Visual Basic 编译器将首先搜索当前文件夹中的标识 DLL。</span><span class="sxs-lookup"><span data-stu-id="3814f-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="3814f-142">它将会使用指定的路径中搜索[/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)编译器选项。</span><span class="sxs-lookup"><span data-stu-id="3814f-142">It will then search in the path that you have specified by using the [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="3814f-143">如果`/sdkpath`不使用编译器选项，编译器将搜索.NET Framework 文件夹中的标识 DLL (`%systemroot%\Microsoft.NET\Framework\versionNumber`)。</span><span class="sxs-lookup"><span data-stu-id="3814f-143">If the `/sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3814f-144">示例</span><span class="sxs-lookup"><span data-stu-id="3814f-144">Example</span></span>  
 <span data-ttu-id="3814f-145">下面的示例演示如何使用`/vbruntime`选项来编译为一个自定义库的引用。</span><span class="sxs-lookup"><span data-stu-id="3814f-145">The following example shows how to use the `/vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="3814f-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3814f-146">See Also</span></span>  
 <span data-ttu-id="3814f-147">[Visual Basic 核心 – Visual Studio 2010 SP1 中新的编译模式](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span><span class="sxs-lookup"><span data-stu-id="3814f-147">[Visual Basic Core – New compilation mode in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx) </span></span>  
<span data-ttu-id="3814f-148"> [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="3814f-148"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="3814f-149"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="3814f-149"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="3814f-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span><span class="sxs-lookup"><span data-stu-id="3814f-150"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span></span>
