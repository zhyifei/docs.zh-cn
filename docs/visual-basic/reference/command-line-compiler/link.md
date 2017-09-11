---
title: "/link (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
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
caps.latest.revision: 27
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
ms.openlocfilehash: 71ecefc898ca37cbf7299d97518e1ce2547a58da
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="link-visual-basic"></a><span data-ttu-id="784c6-102">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="784c6-102">/link (Visual Basic)</span></span>
<span data-ttu-id="784c6-103">使编译器将在指定的程序集的 COM 类型信息提供给当前正在编译项目。</span><span class="sxs-lookup"><span data-stu-id="784c6-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="784c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="784c6-104">Syntax</span></span>  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="784c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="784c6-105">Arguments</span></span>  
  
|<span data-ttu-id="784c6-106">术语</span><span class="sxs-lookup"><span data-stu-id="784c6-106">Term</span></span>|<span data-ttu-id="784c6-107">定义</span><span class="sxs-lookup"><span data-stu-id="784c6-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="784c6-108">必需。</span><span class="sxs-lookup"><span data-stu-id="784c6-108">Required.</span></span> <span data-ttu-id="784c6-109">程序集文件名称的以逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="784c6-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="784c6-110">如果文件名包含空格，则将名称括在引号内。</span><span class="sxs-lookup"><span data-stu-id="784c6-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="784c6-111">备注</span><span class="sxs-lookup"><span data-stu-id="784c6-111">Remarks</span></span>  
 <span data-ttu-id="784c6-112">`/link`选项使你可以部署的应用程序包含嵌入类型信息。</span><span class="sxs-lookup"><span data-stu-id="784c6-112">The `/link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="784c6-113">然后，应用程序可以使用运行时程序集中实现嵌入的类型信息，而无需对运行时程序集引用的类型。</span><span class="sxs-lookup"><span data-stu-id="784c6-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="784c6-114">如果发布了各种版本的运行时程序集，则包含嵌入的类型信息的应用程序可以使用的各种版本，而无需重新编译。</span><span class="sxs-lookup"><span data-stu-id="784c6-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="784c6-115">有关示例，请参阅[演练︰ 嵌入托管程序集的类型](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)。</span><span class="sxs-lookup"><span data-stu-id="784c6-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="784c6-116">使用`/link`选项将特别有用，当您正在使用 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="784c6-116">Using the `/link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="784c6-117">嵌入 COM 类型，以便您的应用程序不再需要主互操作程序集 (PIA) 的目标计算机上。</span><span class="sxs-lookup"><span data-stu-id="784c6-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="784c6-118">`/link`选项指示编译器将嵌入到生成的已编译代码引用的互操作程序集的 COM 类型信息。</span><span class="sxs-lookup"><span data-stu-id="784c6-118">The `/link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="784c6-119">CLSID (GUID) 值被标识的 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="784c6-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="784c6-120">因此，您的应用程序可以安装有相同的 CLSID 值相同的 COM 类型的目标计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="784c6-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="784c6-121">自动执行 Microsoft Office 的应用程序是一个很好示例。</span><span class="sxs-lookup"><span data-stu-id="784c6-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="784c6-122">由于 Office 等应用程序通常在不同版本中保持相同的 CLSID 值，您的应用程序可以使用所引用的 COM 类型，长时间为.NET Framework 4 或更高版本安装在目标计算机上以及你的应用程序使用的方法、 属性或包含在引用的 COM 类型的事件。</span><span class="sxs-lookup"><span data-stu-id="784c6-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="784c6-123">`/link`选项嵌入接口、 结构和委托。</span><span class="sxs-lookup"><span data-stu-id="784c6-123">The `/link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="784c6-124">不支持嵌入 COM 类。</span><span class="sxs-lookup"><span data-stu-id="784c6-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="784c6-125">当在代码中创建嵌入 COM 类型的实例时，必须通过使用适当的接口来创建该实例。</span><span class="sxs-lookup"><span data-stu-id="784c6-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="784c6-126">尝试使用组件类创建嵌入 COM 类型的实例会导致错误。</span><span class="sxs-lookup"><span data-stu-id="784c6-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="784c6-127">若要设置`/link`选项[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]、 添加程序集引用和设置`Embed Interop Types`属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="784c6-127">To set the `/link` option in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="784c6-128">默认值为`Embed Interop Types`属性是**false**。</span><span class="sxs-lookup"><span data-stu-id="784c6-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="784c6-129">如果链接 COM 程序集 （程序集 A） 到其本身引用了另一个 COM 程序集 (程序集 B)，您还必须链接到程序集 B 中，如果下列任一条件为真︰</span><span class="sxs-lookup"><span data-stu-id="784c6-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="784c6-130">程序集 A 中的类型继承自的类型或实现程序集 B 中的接口</span><span class="sxs-lookup"><span data-stu-id="784c6-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="784c6-131">字段、 属性、 事件或程序集 B 中的返回类型或形参类型的方法被调用。</span><span class="sxs-lookup"><span data-stu-id="784c6-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="784c6-132">使用[/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)若要指定一个或多个程序集引用所在的目录。</span><span class="sxs-lookup"><span data-stu-id="784c6-132">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="784c6-133">如[/引用](../../../visual-basic/reference/command-line-compiler/reference.md)编译器选项，则`/link`编译器选项使用频繁地使用引用的 Vbc.rsp 响应文件[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="784c6-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `/link` compiler option uses the Vbc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies.</span></span> <span data-ttu-id="784c6-134">使用[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)编译器选项，如果不希望使用 Vbc.rsp 文件的编译器。</span><span class="sxs-lookup"><span data-stu-id="784c6-134">Use the [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="784c6-135">缩写形式`/link`是`/l`。</span><span class="sxs-lookup"><span data-stu-id="784c6-135">The short form of `/link` is `/l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="784c6-136">泛型和嵌入的类型</span><span class="sxs-lookup"><span data-stu-id="784c6-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="784c6-137">以下各节描述在嵌入互操作类型的应用程序中使用泛型类型的限制。</span><span class="sxs-lookup"><span data-stu-id="784c6-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="784c6-138">泛型接口</span><span class="sxs-lookup"><span data-stu-id="784c6-138">Generic Interfaces</span></span>  
 <span data-ttu-id="784c6-139">不能使用从互操作程序集中嵌入的泛型接口。</span><span class="sxs-lookup"><span data-stu-id="784c6-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="784c6-140">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="784c6-140">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="784c6-141">[!code-vb[VbLinkCompiler #&1;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="784c6-141">[!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]</span></span>  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="784c6-142">拥有的泛型参数的类型</span><span class="sxs-lookup"><span data-stu-id="784c6-142">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="784c6-143">具有其类型嵌入互操作程序集从一个泛型参数类型，如果无法使用该类型为从外部程序集。</span><span class="sxs-lookup"><span data-stu-id="784c6-143">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="784c6-144">此限制不适用于接口。</span><span class="sxs-lookup"><span data-stu-id="784c6-144">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="784c6-145">例如，考虑<xref:Microsoft.Office.Interop.Excel.Range>中定义的接口<xref:Microsoft.Office.Interop.Excel>程序集。</xref:Microsoft.Office.Interop.Excel> </xref:Microsoft.Office.Interop.Excel.Range></span><span class="sxs-lookup"><span data-stu-id="784c6-145">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="784c6-146">如果库嵌入互操作类型从<xref:Microsoft.Office.Interop.Excel>程序集并返回其类型的泛型类型具有参数的方法是的公开<xref:Microsoft.Office.Interop.Excel.Range>接口，该方法必须返回泛型接口，如下面的代码示例中所示。</xref:Microsoft.Office.Interop.Excel.Range> </xref:Microsoft.Office.Interop.Excel></span><span class="sxs-lookup"><span data-stu-id="784c6-146">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 <span data-ttu-id="784c6-147">[!code-vb[VbLinkCompiler #&2;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="784c6-147">[!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]</span></span>  
<span data-ttu-id="784c6-148">[!code-vb[VbLinkCompiler #&3;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="784c6-148">[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]</span></span>  
<span data-ttu-id="784c6-149">[!code-vb[VbLinkCompiler #&4;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="784c6-149">[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]</span></span>  
  
 <span data-ttu-id="784c6-150">在下面的示例中，客户端代码可以调用该方法返回<xref:System.Collections.IList>泛型接口，但没有错误。</xref:System.Collections.IList></span><span class="sxs-lookup"><span data-stu-id="784c6-150">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 <span data-ttu-id="784c6-151">[!code-vb[VbLinkCompiler #&5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="784c6-151">[!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="784c6-152">示例</span><span class="sxs-lookup"><span data-stu-id="784c6-152">Example</span></span>  
 <span data-ttu-id="784c6-153">下面的代码编译源文件`OfficeApp.vb`和引用程序集从`COMData1.dll`和`COMData2.dll`以生成`OfficeApp.exe`。</span><span class="sxs-lookup"><span data-stu-id="784c6-153">The following code compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="784c6-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="784c6-154">See Also</span></span>  
 <span data-ttu-id="784c6-155">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="784c6-155">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="784c6-156"> [演练︰ 嵌入托管程序集中的类型](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span><span class="sxs-lookup"><span data-stu-id="784c6-156"> [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) </span></span>  
<span data-ttu-id="784c6-157"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="784c6-157"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="784c6-158"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="784c6-158"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="784c6-159"> [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) </span><span class="sxs-lookup"><span data-stu-id="784c6-159"> [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) </span></span>  
<span data-ttu-id="784c6-160"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="784c6-160"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="784c6-161"> [COM 互操作介绍](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span><span class="sxs-lookup"><span data-stu-id="784c6-161"> [Introduction to COM Interop](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)</span></span>
