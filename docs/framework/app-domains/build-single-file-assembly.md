---
title: 如何：生成 .NET Framework 单文件程序集
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
dev_langs:
- csharp
- vb
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
ms.openlocfilehash: b7cb06da74a21dab6f60f0d4c3ac1748fcbe4526
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644306"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a><span data-ttu-id="637f6-102">如何：生成 .NET Framework 单文件程序集</span><span class="sxs-lookup"><span data-stu-id="637f6-102">How to: Build a .NET Framework single-file assembly</span></span>

<span data-ttu-id="637f6-103">单文件程序集（最简单的程序集类型）包含类型信息和实现，以及[程序集清单](../../standard/assembly/manifest.md)。</span><span class="sxs-lookup"><span data-stu-id="637f6-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../standard/assembly/manifest.md).</span></span> <span data-ttu-id="637f6-104">可以使用命令行编译器或 Visual Studio 创建面向 .NET Framework 的单文件程序集。</span><span class="sxs-lookup"><span data-stu-id="637f6-104">You can use command-line compilers or Visual Studio to create a single-file assembly that targets the .NET Framework.</span></span> <span data-ttu-id="637f6-105">默认情况下，编译器创建扩展名为 .exe 的程序集文件  。</span><span class="sxs-lookup"><span data-stu-id="637f6-105">By default, the compiler creates an assembly file with an *.exe* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="637f6-106">适用于 C# 和 Visual Basic 的 Visual Studio 只能用于创建单文件程序集。</span><span class="sxs-lookup"><span data-stu-id="637f6-106">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="637f6-107">如果要创建多文件程序集，则必须使用命令行编译器或 Visual C++。</span><span class="sxs-lookup"><span data-stu-id="637f6-107">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="637f6-108">以下步骤说明如何使用命令行编译器创建单文件程序集。</span><span class="sxs-lookup"><span data-stu-id="637f6-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="637f6-109">创建扩展名为 .exe 的程序集</span><span class="sxs-lookup"><span data-stu-id="637f6-109">Create an assembly with an .exe extension</span></span>

<span data-ttu-id="637f6-110">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="637f6-110">At the command prompt, type the following command:</span></span>

<span data-ttu-id="637f6-111">\<compiler command  > \<module name  ></span><span class="sxs-lookup"><span data-stu-id="637f6-111">\<*compiler command*> \<*module name*></span></span>

<span data-ttu-id="637f6-112">在此命令中，“compiler command”  是代码模块中所用语言的编译器命令，“module name”  是要编译为程序集的代码模块的名称。</span><span class="sxs-lookup"><span data-stu-id="637f6-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="637f6-113">以下示例从名为 `myCode` 的代码模块创建名为 myCode.exe 的程序集  。</span><span class="sxs-lookup"><span data-stu-id="637f6-113">The following example creates an assembly named *myCode.exe* from a code module called `myCode`.</span></span>

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="637f6-114">创建扩展名为 .exe 的程序集并指定输出文件名</span><span class="sxs-lookup"><span data-stu-id="637f6-114">Create an assembly with an .exe extension and specify the output file name</span></span>

<span data-ttu-id="637f6-115">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="637f6-115">At the command prompt, type the following command:</span></span>

<span data-ttu-id="637f6-116">\<compiler command  > /out:  \<file name  > \<module name  ></span><span class="sxs-lookup"><span data-stu-id="637f6-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

<span data-ttu-id="637f6-117">在此命令中，“compiler command”  是代码模块中所用语言的编译器命令，“file name”  是输出文件名称，而“module name”  是要编译为程序集的代码模块的名称。</span><span class="sxs-lookup"><span data-stu-id="637f6-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="637f6-118">以下示例从名为 `myCode` 的代码模块创建名为 myAssembly.exe 的程序集  。</span><span class="sxs-lookup"><span data-stu-id="637f6-118">The following example creates an assembly named *myAssembly.exe* from a code module called `myCode`.</span></span>

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a><span data-ttu-id="637f6-119">创建库程序集</span><span class="sxs-lookup"><span data-stu-id="637f6-119">Create library assemblies</span></span>
 <span data-ttu-id="637f6-120">库程序集与类库相似。</span><span class="sxs-lookup"><span data-stu-id="637f6-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="637f6-121">它包含将由其他程序集引用的类型，但没有开始执行的入口点。</span><span class="sxs-lookup"><span data-stu-id="637f6-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

<span data-ttu-id="637f6-122">要创建库程序集，请在命令提示符处键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="637f6-122">To create a library assembly, at the command prompt, type the following command:</span></span>

<span data-ttu-id="637f6-123">\<*compiler command*>  **-t:library** \<*module name*></span><span class="sxs-lookup"><span data-stu-id="637f6-123">\<*compiler command*> **-t:library** \<*module name*></span></span>

<span data-ttu-id="637f6-124">在此命令中，“compiler command”  是代码模块中所用语言的编译器命令，“module name”  是要编译为程序集的代码模块的名称。</span><span class="sxs-lookup"><span data-stu-id="637f6-124">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="637f6-125">也可以使用其他编译器选项，例如 -out: 选项  。</span><span class="sxs-lookup"><span data-stu-id="637f6-125">You can also use other compiler options, such as the **-out:** option.</span></span>

<span data-ttu-id="637f6-126">以下示例从名为 `myCode` 的代码模块创建名为 myCodeAssembly.dll 的库程序集  。</span><span class="sxs-lookup"><span data-stu-id="637f6-126">The following example creates a library assembly named *myCodeAssembly.dll* from a code module called `myCode`.</span></span>

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="637f6-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="637f6-127">See also</span></span>

- [<span data-ttu-id="637f6-128">创建程序集</span><span class="sxs-lookup"><span data-stu-id="637f6-128">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="637f6-129">多文件程序集</span><span class="sxs-lookup"><span data-stu-id="637f6-129">Multifile assemblies</span></span>](multifile-assemblies.md)
- [<span data-ttu-id="637f6-130">如何：生成多文件程序集</span><span class="sxs-lookup"><span data-stu-id="637f6-130">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="637f6-131">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="637f6-131">Program with assemblies</span></span>](../../standard/assembly/index.md)
