---
title: -链接 (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
ms.openlocfilehash: 91eba53eb8094e55af09d406515dad16fc71937d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405297"
---
# <a name="-link-visual-basic"></a><span data-ttu-id="f67ea-102">-链接 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f67ea-102">-link (Visual Basic)</span></span>
<span data-ttu-id="f67ea-103">使编译器让指定程序集中的 COM 类型信息可供当前正在编译的项目使用。</span><span class="sxs-lookup"><span data-stu-id="f67ea-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f67ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="f67ea-104">Syntax</span></span>  
  
```  
-link:fileList  
' -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="f67ea-105">自变量</span><span class="sxs-lookup"><span data-stu-id="f67ea-105">Arguments</span></span>  
  
|<span data-ttu-id="f67ea-106">术语</span><span class="sxs-lookup"><span data-stu-id="f67ea-106">Term</span></span>|<span data-ttu-id="f67ea-107">定义</span><span class="sxs-lookup"><span data-stu-id="f67ea-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="f67ea-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="f67ea-108">Required.</span></span> <span data-ttu-id="f67ea-109">程序集文件名的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="f67ea-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="f67ea-110">如果文件名包含空格，则将名称括在引号内。</span><span class="sxs-lookup"><span data-stu-id="f67ea-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f67ea-111">备注</span><span class="sxs-lookup"><span data-stu-id="f67ea-111">Remarks</span></span>  
 <span data-ttu-id="f67ea-112">`-link` 选项使你可以部署具有嵌入类型信息的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f67ea-112">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="f67ea-113">应用程序随后可以使用运行时程序集中实现嵌入类型信息的类型，而无需引用运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="f67ea-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="f67ea-114">如果发布了各种版本的运行时程序集，则包含嵌入类型信息的应用程序可以使用各种版本，而无需重新编译。</span><span class="sxs-lookup"><span data-stu-id="f67ea-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="f67ea-115">有关示例，请参阅[演练：嵌入托管程序集中的类型](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)。</span><span class="sxs-lookup"><span data-stu-id="f67ea-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="f67ea-116">在使用 COM 互操作时，使用 `-link` 选项会尤其有用。</span><span class="sxs-lookup"><span data-stu-id="f67ea-116">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="f67ea-117">可以嵌入 COM 类型，以便应用程序在目标计算机上不再需要主互操作程序集 (PIA)。</span><span class="sxs-lookup"><span data-stu-id="f67ea-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="f67ea-118">`-link` 选项指示编译器将引用的互操作程序集中的 COM 类型信息嵌入到生成的已编译代码中。</span><span class="sxs-lookup"><span data-stu-id="f67ea-118">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="f67ea-119">COM 类型由 CLSID (GUID) 值进行标识。</span><span class="sxs-lookup"><span data-stu-id="f67ea-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="f67ea-120">因此，应用程序可以在安装了具有相同 CLSID 值的相同 COM 类型的目标计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="f67ea-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="f67ea-121">自动执行 Microsoft Office 的应用程序是一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="f67ea-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="f67ea-122">由于 Office 等应用程序通常在不同版本间保持相同的 CLSID 值，因此只要在目标计算机上安装了 .NET Framework 4 或更高版本，并且应用程序使用引用的 COM 类型中包含的方法、属性或事件，应用程序便可以使用引用的 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="f67ea-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="f67ea-123">`-link` 选项只嵌入接口、结构和委托。</span><span class="sxs-lookup"><span data-stu-id="f67ea-123">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="f67ea-124">不支持嵌入 COM 类。</span><span class="sxs-lookup"><span data-stu-id="f67ea-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f67ea-125">在代码中创建嵌入 COM 类型的实例时，必须使用适当的接口创建该实例。</span><span class="sxs-lookup"><span data-stu-id="f67ea-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="f67ea-126">尝试使用组件类创建嵌入 COM 类型的实例会导致错误。</span><span class="sxs-lookup"><span data-stu-id="f67ea-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="f67ea-127">若要在 Visual Studio 中设置 `-link` 选项，请添加程序集引用并将 `Embed Interop Types` 属性设置为“true”。</span><span class="sxs-lookup"><span data-stu-id="f67ea-127">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="f67ea-128">`Embed Interop Types` 属性的默认值为 **false**。</span><span class="sxs-lookup"><span data-stu-id="f67ea-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="f67ea-129">如果链接到本身引用了其他 COM 程序集（程序集 B）的 COM 程序集（程序集 A），则在满足以下任一条件时，还必须链接到程序集 B：</span><span class="sxs-lookup"><span data-stu-id="f67ea-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="f67ea-130">程序集 A 中的类型继承自程序集 B 中的类型或实现程序集 B 中的接口。</span><span class="sxs-lookup"><span data-stu-id="f67ea-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="f67ea-131">调用具有程序集 B 中的返回类型或参数类型的字段、属性、事件或方法。</span><span class="sxs-lookup"><span data-stu-id="f67ea-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="f67ea-132">使用[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)指定一个或多个程序集引用所在的目录。</span><span class="sxs-lookup"><span data-stu-id="f67ea-132">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="f67ea-133">像[/reference](../../../visual-basic/reference/command-line-compiler/reference.md)编译器选项`-link`编译器选项使用 Vbc.rsp 响应文件引用常用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="f67ea-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `-link` compiler option uses the Vbc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span> <span data-ttu-id="f67ea-134">使用[-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)编译器选项，如果不希望编译器使用 Vbc.rsp 文件。</span><span class="sxs-lookup"><span data-stu-id="f67ea-134">Use the [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="f67ea-135">`-link` 的缩写形式是 `-l`。</span><span class="sxs-lookup"><span data-stu-id="f67ea-135">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="f67ea-136">泛型类型和嵌入类型</span><span class="sxs-lookup"><span data-stu-id="f67ea-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="f67ea-137">以下各部分介绍对在嵌入互操作类型的应用程序中使用泛型类型的限制。</span><span class="sxs-lookup"><span data-stu-id="f67ea-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="f67ea-138">泛型接口</span><span class="sxs-lookup"><span data-stu-id="f67ea-138">Generic Interfaces</span></span>  
 <span data-ttu-id="f67ea-139">不能使用从互操作程序集中嵌入的泛型接口。</span><span class="sxs-lookup"><span data-stu-id="f67ea-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="f67ea-140">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="f67ea-140">This is shown in the following example.</span></span>  
  
 [!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="f67ea-141">具有泛型参数的类型</span><span class="sxs-lookup"><span data-stu-id="f67ea-141">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="f67ea-142">对于具有类型是从互操作程序集嵌入的泛型参数的类型，如果该类型来自外部程序集，则无法使用这种类型。</span><span class="sxs-lookup"><span data-stu-id="f67ea-142">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="f67ea-143">此限制不适用于接口。</span><span class="sxs-lookup"><span data-stu-id="f67ea-143">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="f67ea-144">例如，考虑在 <xref:Microsoft.Office.Interop.Excel> 程序集中定义的 <xref:Microsoft.Office.Interop.Excel.Range> 接口。</span><span class="sxs-lookup"><span data-stu-id="f67ea-144">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="f67ea-145">如果某个库从 <xref:Microsoft.Office.Interop.Excel> 程序集嵌入互操作类型，并且公开的一个方法返回具有类型是 <xref:Microsoft.Office.Interop.Excel.Range> 接口的参数的泛型类型，则该方法必须返回泛型接口，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="f67ea-145">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]  
[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]  
[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]  
  
 <span data-ttu-id="f67ea-146">在下面的示例中，客户端代码可以调用返回 <xref:System.Collections.IList> 泛型接口的方法而不会出现错误。</span><span class="sxs-lookup"><span data-stu-id="f67ea-146">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="f67ea-147">示例</span><span class="sxs-lookup"><span data-stu-id="f67ea-147">Example</span></span>  
 <span data-ttu-id="f67ea-148">下面的命令行编译源文件`OfficeApp.vb`和引用程序集从`COMData1.dll`并`COMData2.dll`以生成`OfficeApp.exe`。</span><span class="sxs-lookup"><span data-stu-id="f67ea-148">The following command line compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```console  
vbc -link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f67ea-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="f67ea-149">See Also</span></span>  
 [<span data-ttu-id="f67ea-150">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="f67ea-150">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="f67ea-151">演练：嵌入托管程序集中的类型</span><span class="sxs-lookup"><span data-stu-id="f67ea-151">Walkthrough: Embedding Types from Managed Assemblies</span></span>](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="f67ea-152">-参考 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f67ea-152">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="f67ea-153">-noconfig</span><span class="sxs-lookup"><span data-stu-id="f67ea-153">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="f67ea-154">-libpath</span><span class="sxs-lookup"><span data-stu-id="f67ea-154">-libpath</span></span>](../../../visual-basic/reference/command-line-compiler/libpath.md)  
 [<span data-ttu-id="f67ea-155">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="f67ea-155">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="f67ea-156">COM 互操作介绍</span><span class="sxs-lookup"><span data-stu-id="f67ea-156">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
