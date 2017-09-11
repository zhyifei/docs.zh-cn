---
title: "如何：生成单文件程序集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1a584e6ded79489e5e33b07d02dde618541c6cc8
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="07616-102">如何：生成单文件程序集</span><span class="sxs-lookup"><span data-stu-id="07616-102">How to: Build a Single-File Assembly</span></span>
<span data-ttu-id="07616-103">单文件程序集（最简单的程序集类型）包含类型信息和实现，以及[程序集清单](../../../docs/framework/app-domains/assembly-manifest.md)。</span><span class="sxs-lookup"><span data-stu-id="07616-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="07616-104">可以使用命令行编译器或 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 创建单文件程序集。</span><span class="sxs-lookup"><span data-stu-id="07616-104">You can use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to create a single-file assembly.</span></span> <span data-ttu-id="07616-105">默认情况下，编译器创建扩展名为 .exe 的程序集文件。</span><span class="sxs-lookup"><span data-stu-id="07616-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07616-106">适用于 C# 和 Visual Basic 的 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 只能用于创建单文件程序集。</span><span class="sxs-lookup"><span data-stu-id="07616-106">[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="07616-107">如果要创建多文件程序集，则必须使用命令行编译器或用于 Visual C++ 的 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="07616-107">If you want to create multifile assemblies, you must use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for Visual C++.</span></span>  
  
 <span data-ttu-id="07616-108">以下步骤说明如何使用命令行编译器创建单文件程序集。</span><span class="sxs-lookup"><span data-stu-id="07616-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="07616-109">创建扩展名为 .exe 的程序集</span><span class="sxs-lookup"><span data-stu-id="07616-109">To create an assembly with an .exe extension</span></span>  
  
1.  <span data-ttu-id="07616-110">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="07616-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="07616-111">\<compiler command> \<module name></span><span class="sxs-lookup"><span data-stu-id="07616-111">\<*compiler command*> \<*module name*></span></span>  
  
     <span data-ttu-id="07616-112">在此命令中，“compiler command”是代码模块中所用语言的编译器命令，“module name”是要编译为程序集的代码模块的名称。</span><span class="sxs-lookup"><span data-stu-id="07616-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="07616-113">以下示例从名为 `myCode` 的代码模块创建名为 `myCode.exe` 的程序集。</span><span class="sxs-lookup"><span data-stu-id="07616-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="07616-114">创建扩展名为 .exe 的程序集并指定输出文件名</span><span class="sxs-lookup"><span data-stu-id="07616-114">To create an assembly with an .exe extension and specify the output file name</span></span>  
  
1.  <span data-ttu-id="07616-115">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="07616-115">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="07616-116">\<compiler command> /out:\<file name> \<module name></span><span class="sxs-lookup"><span data-stu-id="07616-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>  
  
     <span data-ttu-id="07616-117">在此命令中，“compiler command”是代码模块中所用语言的编译器命令，“file name”是输出文件名称，而“module name”是要编译为程序集的代码模块的名称。</span><span class="sxs-lookup"><span data-stu-id="07616-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="07616-118">以下示例从名为 `myCode` 的代码模块创建名为 `myAssembly.exe` 的程序集。</span><span class="sxs-lookup"><span data-stu-id="07616-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a><span data-ttu-id="07616-119">创建库程序集</span><span class="sxs-lookup"><span data-stu-id="07616-119">Creating Library Assemblies</span></span>  
 <span data-ttu-id="07616-120">库程序集与类库相似。</span><span class="sxs-lookup"><span data-stu-id="07616-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="07616-121">它包含将由其他程序集引用的类型，但没有开始执行的入口点。</span><span class="sxs-lookup"><span data-stu-id="07616-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>  
  
#### <a name="to-create-a-library-assembly"></a><span data-ttu-id="07616-122">创建库程序集</span><span class="sxs-lookup"><span data-stu-id="07616-122">To create a library assembly</span></span>  
  
1.  <span data-ttu-id="07616-123">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="07616-123">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="07616-124">\<compiler command> /t:library \<module name></span><span class="sxs-lookup"><span data-stu-id="07616-124">\<*compiler command*> **/t:library** \<*module name*></span></span>  
  
     <span data-ttu-id="07616-125">在此命令中，“compiler command”是代码模块中所用语言的编译器命令，“module name”是要编译为程序集的代码模块的名称。</span><span class="sxs-lookup"><span data-stu-id="07616-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="07616-126">也可以使用其他编译器选项，例如 /out: 选项。</span><span class="sxs-lookup"><span data-stu-id="07616-126">You can also use other compiler options, such as the **/out:** option.</span></span>  
  
 <span data-ttu-id="07616-127">以下示例从名为 `myCode` 的代码模块创建名为 `myCodeAssembly.dll` 的库程序集。</span><span class="sxs-lookup"><span data-stu-id="07616-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="07616-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07616-128">See Also</span></span>  
 <span data-ttu-id="07616-129">[创建程序集](../../../docs/framework/app-domains/create-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="07616-129">[Creating Assemblies](../../../docs/framework/app-domains/create-assemblies.md) </span></span>  
 <span data-ttu-id="07616-130">[多文件程序集](../../../docs/framework/app-domains/multifile-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="07616-130">[Multifile Assemblies](../../../docs/framework/app-domains/multifile-assemblies.md) </span></span>  
 <span data-ttu-id="07616-131">[如何：生成多文件程序集](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="07616-131">[How to: Build a Multifile Assembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span></span>  
 [<span data-ttu-id="07616-132">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="07616-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)

