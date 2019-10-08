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
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005052"
---
# <a name="-vbruntime"></a><span data-ttu-id="0b6e5-102">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="0b6e5-102">-vbruntime</span></span>
<span data-ttu-id="0b6e5-103">指定编译器应在不引用 Visual Basic 运行库的情况下进行编译，或在引用特定运行库的情况下进行编译。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-103">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b6e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b6e5-104">Syntax</span></span>  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b6e5-105">参数</span><span class="sxs-lookup"><span data-stu-id="0b6e5-105">Arguments</span></span>  
 \-  
 <span data-ttu-id="0b6e5-106">在不引用 Visual Basic 运行时库的情况下编译。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-106">Compile without a reference to the Visual Basic Runtime Library.</span></span>  
  
 \+  
 <span data-ttu-id="0b6e5-107">使用对默认 Visual Basic 运行时库的引用进行编译。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-107">Compile with a reference to the default Visual Basic Runtime Library.</span></span>  
  
 \*  
 <span data-ttu-id="0b6e5-108">在不引用 Visual Basic 运行时库的情况下进行编译，并将 Visual Basic 运行时库中的核心功能嵌入到程序集中。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-108">Compile without a reference to the Visual Basic Runtime Library, and embed core functionality from the Visual Basic Runtime Library into the assembly.</span></span>  
  
 `path`  
 <span data-ttu-id="0b6e5-109">使用对指定库（DLL）的引用进行编译。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-109">Compile with a reference to the specified library (DLL).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b6e5-110">备注</span><span class="sxs-lookup"><span data-stu-id="0b6e5-110">Remarks</span></span>  
 <span data-ttu-id="0b6e5-111">使用 `-vbruntime` 编译器选项，可以指定编译器应在不引用 Visual Basic 运行库的情况下编译。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-111">The `-vbruntime` compiler option enables you to specify that the compiler should compile without a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="0b6e5-112">如果在不引用 Visual Basic 运行时库的情况下进行编译，则会记录生成对 Visual Basic 运行时帮助程序的调用的代码或语言构造的错误或警告。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-112">If you compile without a reference to the Visual Basic Runtime Library, errors or warnings are logged on code or language constructs that generate a call to a Visual Basic runtime helper.</span></span> <span data-ttu-id="0b6e5-113">（ *Visual Basic 运行时帮助器*是一个在运行时调用的函数，用于执行特定的语言语义。）</span><span class="sxs-lookup"><span data-stu-id="0b6e5-113">(A *Visual Basic runtime helper* is a function defined in Microsoft.VisualBasic.dll that is called at runtime to execute a specific language semantic.)</span></span>  
  
 <span data-ttu-id="0b6e5-114">@No__t-0 选项将产生与未指定 @no__t 1 开关时发生的相同行为。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-114">The `-vbruntime+` option produces the same behavior that occurs if no `-vbruntime` switch is specified.</span></span> <span data-ttu-id="0b6e5-115">你可以使用 `-vbruntime+` 选项来重写以前的 @no__t 1 开关。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-115">You can use the `-vbruntime+` option to override previous `-vbruntime` switches.</span></span>  
  
 <span data-ttu-id="0b6e5-116">使用 @no__t 或 @no__t 2 选项时，@no__t 0 类型的大多数对象不可用。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-116">Most objects of the `My` type are unavailable when you use the `-vbruntime-` or `-vbruntime:path` options.</span></span>  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a><span data-ttu-id="0b6e5-117">嵌入 Visual Basic 运行时核心功能</span><span class="sxs-lookup"><span data-stu-id="0b6e5-117">Embedding Visual Basic Runtime core functionality</span></span>  
 <span data-ttu-id="0b6e5-118">使用 @no__t 的选项，可以在不引用运行库的情况下编译。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-118">The `-vbruntime*` option enables you to compile without a reference to a runtime library.</span></span> <span data-ttu-id="0b6e5-119">相反，将 Visual Basic 运行时库中的核心功能嵌入用户程序集。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-119">Instead, core functionality from the Visual Basic Runtime Library is embedded in the user assembly.</span></span> <span data-ttu-id="0b6e5-120">如果你的应用程序在不包含 Visual Basic 运行时的平台上运行，则可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-120">You can use this option if your application runs on platforms that do not contain the Visual Basic runtime.</span></span>  
  
 <span data-ttu-id="0b6e5-121">以下运行时成员嵌入：</span><span class="sxs-lookup"><span data-stu-id="0b6e5-121">The following runtime members are embedded:</span></span>  
  
- <span data-ttu-id="0b6e5-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> 类</span><span class="sxs-lookup"><span data-stu-id="0b6e5-122"><xref:Microsoft.VisualBasic.CompilerServices.Conversions> class</span></span>  
  
- <span data-ttu-id="0b6e5-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> 方法</span><span class="sxs-lookup"><span data-stu-id="0b6e5-123"><xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> method</span></span>  
  
- <span data-ttu-id="0b6e5-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> 方法</span><span class="sxs-lookup"><span data-stu-id="0b6e5-124"><xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> method</span></span>  
  
- <span data-ttu-id="0b6e5-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> 方法</span><span class="sxs-lookup"><span data-stu-id="0b6e5-125"><xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> method</span></span>  
  
- <span data-ttu-id="0b6e5-126"><xref:Microsoft.VisualBasic.Constants.vbBack> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-126"><xref:Microsoft.VisualBasic.Constants.vbBack> constant</span></span>  
  
- <span data-ttu-id="0b6e5-127"><xref:Microsoft.VisualBasic.Constants.vbCr> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-127"><xref:Microsoft.VisualBasic.Constants.vbCr> constant</span></span>  
  
- <span data-ttu-id="0b6e5-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-128"><xref:Microsoft.VisualBasic.Constants.vbCrLf> constant</span></span>  
  
- <span data-ttu-id="0b6e5-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-129"><xref:Microsoft.VisualBasic.Constants.vbFormFeed> constant</span></span>  
  
- <span data-ttu-id="0b6e5-130"><xref:Microsoft.VisualBasic.Constants.vbLf> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-130"><xref:Microsoft.VisualBasic.Constants.vbLf> constant</span></span>  
  
- <span data-ttu-id="0b6e5-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-131"><xref:Microsoft.VisualBasic.Constants.vbNewLine> constant</span></span>  
  
- <span data-ttu-id="0b6e5-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-132"><xref:Microsoft.VisualBasic.Constants.vbNullChar> constant</span></span>  
  
- <span data-ttu-id="0b6e5-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-133"><xref:Microsoft.VisualBasic.Constants.vbNullString> constant</span></span>  
  
- <span data-ttu-id="0b6e5-134"><xref:Microsoft.VisualBasic.Constants.vbTab> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-134"><xref:Microsoft.VisualBasic.Constants.vbTab> constant</span></span>  
  
- <span data-ttu-id="0b6e5-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> 常量</span><span class="sxs-lookup"><span data-stu-id="0b6e5-135"><xref:Microsoft.VisualBasic.Constants.vbVerticalTab> constant</span></span>  
  
- <span data-ttu-id="0b6e5-136">@No__t 类型的某些对象</span><span class="sxs-lookup"><span data-stu-id="0b6e5-136">Some objects of the `My` type</span></span>  
  
 <span data-ttu-id="0b6e5-137">如果使用 `-vbruntime*` 选项进行编译，并且你的代码引用了未嵌入核心功能的 Visual Basic 运行时库中的成员，则编译器将返回一个错误，指示该成员不可用。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-137">If you compile using the `-vbruntime*` option and your code references a member from the Visual Basic Runtime Library that is not embedded with the core functionality, the compiler returns an error that indicates that the member is not available.</span></span>  
  
## <a name="referencing-a-specified-library"></a><span data-ttu-id="0b6e5-138">引用指定的库</span><span class="sxs-lookup"><span data-stu-id="0b6e5-138">Referencing a specified library</span></span>  
 <span data-ttu-id="0b6e5-139">您可以使用 @no__t 参数通过对自定义运行库的引用进行编译，而不是使用默认 Visual Basic 运行时库。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-139">You can use the `path` argument to compile with a reference to a custom runtime library instead of the default Visual Basic Runtime Library.</span></span>  
  
 <span data-ttu-id="0b6e5-140">如果 @no__t 参数的值是 DLL 的完全限定路径，则编译器将使用该文件作为运行时库。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-140">If the value for the `path` argument is a fully qualified path to a DLL, the compiler will use that file as the runtime library.</span></span> <span data-ttu-id="0b6e5-141">如果 @no__t 参数的值不是 DLL 的完全限定路径，则 Visual Basic 编译器将首先在当前文件夹中搜索标识的 DLL。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-141">If the value for the `path` argument is not a fully qualified path to a DLL, the Visual Basic compiler will search for the identified DLL in the current folder first.</span></span> <span data-ttu-id="0b6e5-142">然后，它将在你使用[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)编译器选项指定的路径中进行搜索。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-142">It will then search in the path that you have specified by using the [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) compiler option.</span></span> <span data-ttu-id="0b6e5-143">如果未使用 `-sdkpath` 编译器选项，编译器将在 .NET Framework 文件夹（`%systemroot%\Microsoft.NET\Framework\versionNumber`）中搜索标识的 DLL。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-143">If the `-sdkpath` compiler option is not used, the compiler will search for the identified DLL in the .NET Framework folder (`%systemroot%\Microsoft.NET\Framework\versionNumber`).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b6e5-144">示例</span><span class="sxs-lookup"><span data-stu-id="0b6e5-144">Example</span></span>  
 <span data-ttu-id="0b6e5-145">下面的示例演示如何使用 `-vbruntime` 选项进行编译，使其引用自定义库。</span><span class="sxs-lookup"><span data-stu-id="0b6e5-145">The following example shows how to use the `-vbruntime` option to compile with a reference to a custom library.</span></span>  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b6e5-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b6e5-146">See also</span></span>

- [<span data-ttu-id="0b6e5-147">Visual Basic 核心– Visual Studio 2010 SP1 中的新编译模式</span><span class="sxs-lookup"><span data-stu-id="0b6e5-147">Visual Basic Core – New compilation mode in Visual Studio 2010 SP1</span></span>](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [<span data-ttu-id="0b6e5-148">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="0b6e5-148">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0b6e5-149">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="0b6e5-149">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="0b6e5-150">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="0b6e5-150">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
