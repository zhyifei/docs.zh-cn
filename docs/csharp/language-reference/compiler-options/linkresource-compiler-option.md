---
title: "-linkresource (C# 编译器选项)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /linkresource
dev_langs:
- CSharp
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 022d6c1a53eab98fc033c902f903e7bc66e6da3f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="linkresource-c-compiler-options"></a><span data-ttu-id="62da8-102">/linkresource (C# 编译器选项)</span><span class="sxs-lookup"><span data-stu-id="62da8-102">/linkresource (C# Compiler Options)</span></span>
<span data-ttu-id="62da8-103">在输出文件中创建指向 .NET Framework 资源的链接。</span><span class="sxs-lookup"><span data-stu-id="62da8-103">Creates a link to a .NET Framework resource in the output file.</span></span> <span data-ttu-id="62da8-104">不会在输出文件中添加资源文件。</span><span class="sxs-lookup"><span data-stu-id="62da8-104">The resource file is not added to the output file.</span></span> <span data-ttu-id="62da8-105">这不同于会在输出文件中嵌入资源文件的 [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) 选项。</span><span class="sxs-lookup"><span data-stu-id="62da8-105">This differs from the [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) option which does embed a resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62da8-106">语法</span><span class="sxs-lookup"><span data-stu-id="62da8-106">Syntax</span></span>  
  
```console  
/linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="62da8-107">参数</span><span class="sxs-lookup"><span data-stu-id="62da8-107">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="62da8-108">希望从程序集链接到的 .NET Framework 资源文件。</span><span class="sxs-lookup"><span data-stu-id="62da8-108">The .NET Framework resource file to which you want to link from the assembly.</span></span>  
  
 <span data-ttu-id="62da8-109">`identifier`（可选）</span><span class="sxs-lookup"><span data-stu-id="62da8-109">`identifier` (optional)</span></span>  
 <span data-ttu-id="62da8-110">资源的逻辑名称；用于加载资源的名称。</span><span class="sxs-lookup"><span data-stu-id="62da8-110">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="62da8-111">默认值是文件的名称。</span><span class="sxs-lookup"><span data-stu-id="62da8-111">The default is the name of the file.</span></span>  
  
 <span data-ttu-id="62da8-112">`accessibility-modifier`（可选）</span><span class="sxs-lookup"><span data-stu-id="62da8-112">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="62da8-113">资源的可访问性：public 或 private。</span><span class="sxs-lookup"><span data-stu-id="62da8-113">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="62da8-114">默认值为 public。</span><span class="sxs-lookup"><span data-stu-id="62da8-114">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62da8-115">备注</span><span class="sxs-lookup"><span data-stu-id="62da8-115">Remarks</span></span>  
 <span data-ttu-id="62da8-116">默认情况下，如果使用 C# 编译器创建链接资源，则这些资源在程序集中是公有的。</span><span class="sxs-lookup"><span data-stu-id="62da8-116">By default, linked resources are public in the assembly when they are created with the C# compiler.</span></span> <span data-ttu-id="62da8-117">若要使资源变为私有，请将 `private` 指定为可访问性修饰符。</span><span class="sxs-lookup"><span data-stu-id="62da8-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="62da8-118">不允许使用 `public` 或 `private` 以外的任何其他修饰符。</span><span class="sxs-lookup"><span data-stu-id="62da8-118">No other modifier other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="62da8-119">/linkresource 需要某个 [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 选项（/target:module 除外）。</span><span class="sxs-lookup"><span data-stu-id="62da8-119">**/linkresource** requires one of the [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) options other than **/target:module**.</span></span>  
  
 <span data-ttu-id="62da8-120">例如，如果 `filename` 是由 [Resgen.exe](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) 创建的或在开发环境中创建的 .NET Framework 资源文件，则可使用 <xref:System.Resources> 命名空间中的成员来访问它。</span><span class="sxs-lookup"><span data-stu-id="62da8-120">If `filename` is a .NET Framework resource file created, for example, by [Resgen.exe](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="62da8-121">有关更多信息，请参见<xref:System.Resources.ResourceManager?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="62da8-121">For more information, see <xref:System.Resources.ResourceManager?displayProperty=fullName>.</span></span> <span data-ttu-id="62da8-122">对于所有其他资源，请使用 <xref:System.Reflection.Assembly> 类中的 `GetManifestResource`* 方法在运行时访问资源。</span><span class="sxs-lookup"><span data-stu-id="62da8-122">For all other resources, use the `GetManifestResource`* methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="62da8-123">`filename` 中指定的文件可为任何格式。</span><span class="sxs-lookup"><span data-stu-id="62da8-123">The file specified in `filename` can be any format.</span></span> <span data-ttu-id="62da8-124">例如，你可能希望生成程序集的本机 DLL 部分，从而可将它安装到全局程序集缓存中，并且可从该程序集中的托管代码访问它。</span><span class="sxs-lookup"><span data-stu-id="62da8-124">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span> <span data-ttu-id="62da8-125">以下示例中的第二个示例演示了如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="62da8-125">The second of the following examples shows how to do this.</span></span> <span data-ttu-id="62da8-126">可在程序集链接器中执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="62da8-126">You can do the same thing in the Assembly Linker.</span></span> <span data-ttu-id="62da8-127">以下示例中的第三个示例演示了如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="62da8-127">The third of the following examples shows how to do this.</span></span> <span data-ttu-id="62da8-128">有关详细信息，请参阅 [Al.exe（程序集链接器）](https://msdn.microsoft.com/library/c405shex)和[使用程序集和全局程序集缓存](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)。</span><span class="sxs-lookup"><span data-stu-id="62da8-128">For more information, see [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) and [Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).</span></span>  
  
 <span data-ttu-id="62da8-129">/linkres 是 /linkresource 的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="62da8-129">**/linkres** is the short form of **/linkresource**.</span></span>  
  
 <span data-ttu-id="62da8-130">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="62da8-130">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62da8-131">示例</span><span class="sxs-lookup"><span data-stu-id="62da8-131">Example</span></span>  
 <span data-ttu-id="62da8-132">编译 `in.cs` 并链接到资源文件 `rf.resource`：</span><span class="sxs-lookup"><span data-stu-id="62da8-132">Compile `in.cs` and link to resource file `rf.resource`:</span></span>  
  
```console  
csc /linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a><span data-ttu-id="62da8-133">示例</span><span class="sxs-lookup"><span data-stu-id="62da8-133">Example</span></span>  
 <span data-ttu-id="62da8-134">将 `A.cs` 编译为 DLL，链接到本机 DLL N.dll，并将输出文件放在全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="62da8-134">Compile `A.cs` into a DLL, link to a native DLL N.dll, and put the output in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="62da8-135">在此示例中，A.dll 和 N.dll 都存在于 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="62da8-135">In this example, both A.dll and N.dll will reside in the GAC.</span></span>  
  
```console  
csc /linkresource:N.dll /t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a><span data-ttu-id="62da8-136">示例</span><span class="sxs-lookup"><span data-stu-id="62da8-136">Example</span></span>  
 <span data-ttu-id="62da8-137">此示例执行的操作与上一示例相同，但使用程序集链接器选项执行。</span><span class="sxs-lookup"><span data-stu-id="62da8-137">This example does the same thing as the previous one, but by using Assembly Linker options.</span></span>  
  
```console  
csc /t:module A.cs  
al /out:A.dll A.netmodule /link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="62da8-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62da8-138">See Also</span></span>  
 <span data-ttu-id="62da8-139">[（C# 编译器选项）](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="62da8-139">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="62da8-140">[Al.exe（程序集链接器）](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="62da8-140">[Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
 <span data-ttu-id="62da8-141">[使用程序集和全局程序集缓存](../../../framework/app-domains/working-with-assemblies-and-the-gac.md) </span><span class="sxs-lookup"><span data-stu-id="62da8-141">[Working with Assemblies and the Global Assembly Cache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md) </span></span>  
 [<span data-ttu-id="62da8-142">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="62da8-142">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

