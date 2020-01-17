---
title: 如何：使用强名称为程序集签名
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 64f3a51b29a7116c736fea0e76465a4a73c640c2
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75738779"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a><span data-ttu-id="b5714-102">如何：使用强名称为程序集签名</span><span class="sxs-lookup"><span data-stu-id="b5714-102">How to: Sign an assembly with a strong name</span></span>

> [!NOTE]
> <span data-ttu-id="b5714-103">虽然 .NET Core 支持强名称程序集，而且 .NET Core 库中的所有程序集均已签名，但大多数第三方程序集不需要强名称。</span><span class="sxs-lookup"><span data-stu-id="b5714-103">Although .NET Core supports strong-named assemblies, and all assemblies in the .NET Core library are signed, the majority of third-party assemblies do not need strong names.</span></span> <span data-ttu-id="b5714-104">有关详细信息，请参阅 GitHub 上的[强名称签名](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md)。</span><span class="sxs-lookup"><span data-stu-id="b5714-104">For more information, see [Strong Name Signing](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) on GitHub.</span></span>

<span data-ttu-id="b5714-105">可通过许多方法为程序集签署强名称：</span><span class="sxs-lookup"><span data-stu-id="b5714-105">There are a number of ways to sign an assembly with a strong name:</span></span>  
  
- <span data-ttu-id="b5714-106">在 Visual Studio 中，通过使用项目的 **“属性”** 对话框中的 **“签名”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5714-106">By using the **Signing** tab in a project's **Properties** dialog box in Visual Studio.</span></span> <span data-ttu-id="b5714-107">这是为程序集签署强名称的最简单且最方便的方法。</span><span class="sxs-lookup"><span data-stu-id="b5714-107">This is the easiest and most convenient way to sign an assembly with a strong name.</span></span>  
  
- <span data-ttu-id="b5714-108">通过使用[程序集链接器 (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) 来链接 .NET Framework 代码模块（.netmodule 文件）与密钥文件  。</span><span class="sxs-lookup"><span data-stu-id="b5714-108">By using the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) to link a .NET Framework code module (a *.netmodule* file) with a key file.</span></span>  
  
- <span data-ttu-id="b5714-109">通过使用程序集特性将强名称信息插入代码中。</span><span class="sxs-lookup"><span data-stu-id="b5714-109">By using assembly attributes to insert the strong name information into your code.</span></span> <span data-ttu-id="b5714-110">你可以使用 <xref:System.Reflection.AssemblyKeyFileAttribute> 或 <xref:System.Reflection.AssemblyKeyNameAttribute> 特性，具体取决于要使用的密钥文件所在的位置。</span><span class="sxs-lookup"><span data-stu-id="b5714-110">You can use either the <xref:System.Reflection.AssemblyKeyFileAttribute> or the <xref:System.Reflection.AssemblyKeyNameAttribute> attribute, depending on where the key file to be used is located.</span></span>  
  
- <span data-ttu-id="b5714-111">通过使用编译器选项。</span><span class="sxs-lookup"><span data-stu-id="b5714-111">By using compiler options.</span></span>  
  
 <span data-ttu-id="b5714-112">要使用强名称为程序集签名，必须具有加密密钥对。</span><span class="sxs-lookup"><span data-stu-id="b5714-112">You must have a cryptographic key pair to sign an assembly with a strong name.</span></span> <span data-ttu-id="b5714-113">有关创建密钥对的详细信息，请参阅[如何：创建公钥/私钥对](create-public-private-key-pair.md)。</span><span class="sxs-lookup"><span data-stu-id="b5714-113">For more information about creating a key pair, see [How to: Create a public-private key pair](create-public-private-key-pair.md).</span></span>  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a><span data-ttu-id="b5714-114">使用 Visual Studio 创建程序集并使用强名称为程序集签名</span><span class="sxs-lookup"><span data-stu-id="b5714-114">Create and sign an assembly with a strong name by using Visual Studio</span></span>  
  
1. <span data-ttu-id="b5714-115">在“解决方案资源管理器”  中，打开项目的快捷菜单，然后选择“属性”  。</span><span class="sxs-lookup"><span data-stu-id="b5714-115">In **Solution Explorer**, open the shortcut menu for the project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="b5714-116">选择 **“签名”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5714-116">Choose the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="b5714-117">选择“为程序集签名”  框。</span><span class="sxs-lookup"><span data-stu-id="b5714-117">Select the **Sign the assembly** box.</span></span>  
  
4. <span data-ttu-id="b5714-118">在“选择强名称密钥文件”框中，选择“浏览”，然后导航到密钥文件   。</span><span class="sxs-lookup"><span data-stu-id="b5714-118">In the **Choose a strong name key file** box, choose **Browse**, and then navigate to the key file.</span></span> <span data-ttu-id="b5714-119">若要创建新的密钥文件，请选择“新建”，并在“创建强名称密钥”对话框中输入其名称   。</span><span class="sxs-lookup"><span data-stu-id="b5714-119">To create a new key file, choose **New** and enter its name in the **Create Strong Name Key** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5714-120">为了[延迟为程序集签名](delay-sign.md)，请选择公钥文件。</span><span class="sxs-lookup"><span data-stu-id="b5714-120">In order to [delay sign an assembly](delay-sign.md), choose a public key file.</span></span>  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a><span data-ttu-id="b5714-121">使用程序集链接器创建程序集并使用强名称为程序集签名</span><span class="sxs-lookup"><span data-stu-id="b5714-121">Create and sign an assembly with a strong name by using the Assembly Linker</span></span>  
  
<span data-ttu-id="b5714-122">在 [Visual Studio 开发人员命令提示](../../framework/tools/developer-command-prompt-for-vs.md)处，输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="b5714-122">At the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), enter the following command:</span></span>  

<span data-ttu-id="b5714-123">**al** **/out:** \<*assemblyName*>  *\<moduleName>* **/keyfile:** \<*keyfileName*></span><span class="sxs-lookup"><span data-stu-id="b5714-123">**al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*></span></span>  

<span data-ttu-id="b5714-124">其中：</span><span class="sxs-lookup"><span data-stu-id="b5714-124">Where:</span></span>  

- <span data-ttu-id="b5714-125">assemblyName 是程序集链接器将发出的强签名程序集（.dll 或 .exe 文件）的名称    。</span><span class="sxs-lookup"><span data-stu-id="b5714-125">*assemblyName* is the name of the strongly signed assembly (a *.dll* or *.exe* file) that Assembly Linker will emit.</span></span>  
  
- <span data-ttu-id="b5714-126">moduleName 是包含一个或多个类型的 .NET Framework 代码模块（.netmodule 文件）的名称   。</span><span class="sxs-lookup"><span data-stu-id="b5714-126">*moduleName* is the name of a .NET Framework code module (a *.netmodule* file) that includes one or more types.</span></span> <span data-ttu-id="b5714-127">可通过在 C# 或 Visual Basic 中使用 `/target:module` 开关对代码进行编译来创建.netmodule 文件  。</span><span class="sxs-lookup"><span data-stu-id="b5714-127">You can create a *.netmodule* file by compiling your code with the `/target:module` switch in C# or Visual Basic.</span></span>
  
- <span data-ttu-id="b5714-128">keyfileName 是包含密钥对的容器或文件的名称  。</span><span class="sxs-lookup"><span data-stu-id="b5714-128">*keyfileName* is the name of the container or file that contains the key pair.</span></span> <span data-ttu-id="b5714-129">程序集链接器解释与当前目录相关的相对路径。</span><span class="sxs-lookup"><span data-stu-id="b5714-129">Assembly Linker interprets a relative path in relation to the current directory.</span></span>  

<span data-ttu-id="b5714-130">下面的示例使用密钥文件 sgKey.snk 为程序集 MyAssembly.dll 签署强名称   。</span><span class="sxs-lookup"><span data-stu-id="b5714-130">The following example signs the assembly *MyAssembly.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
<span data-ttu-id="b5714-131">有关此工具的详细信息，请参阅 [程序集链接器](../../framework/tools/al-exe-assembly-linker.md)。</span><span class="sxs-lookup"><span data-stu-id="b5714-131">For more information about this tool, see [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).</span></span>  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a><span data-ttu-id="b5714-132">使用属性为程序集签署强名称</span><span class="sxs-lookup"><span data-stu-id="b5714-132">Sign an assembly with a strong name by using attributes</span></span>  
  
1. <span data-ttu-id="b5714-133">将 <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> 或 <xref:System.Reflection.AssemblyKeyNameAttribute> 特性添加到源代码文件中，并指定包含为程序集签署强名称时要使用的密钥对的文件或容器的名称。</span><span class="sxs-lookup"><span data-stu-id="b5714-133">Add the <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute to your source code file, and specify the name of the file or container that contains the key pair to use when signing the assembly with a strong name.</span></span>  
   
2. <span data-ttu-id="b5714-134">通常会编译源代码文件。</span><span class="sxs-lookup"><span data-stu-id="b5714-134">Compile the source code file normally.</span></span>  
   
   > [!NOTE]
   > <span data-ttu-id="b5714-135">当 C# 和 Visual Basic 编译器在源代码中遇到 <xref:System.Reflection.AssemblyKeyFileAttribute> 或 <xref:System.Reflection.AssemblyKeyNameAttribute> 特性时，会发出编译器警告（分别为 CS1699 和 BC41008）。</span><span class="sxs-lookup"><span data-stu-id="b5714-135">The C# and Visual Basic compilers issue compiler warnings (CS1699 and BC41008, respectively) when they encounter the <xref:System.Reflection.AssemblyKeyFileAttribute> or <xref:System.Reflection.AssemblyKeyNameAttribute> attribute in source code.</span></span> <span data-ttu-id="b5714-136">你可以忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="b5714-136">You can ignore the warnings.</span></span>  

<span data-ttu-id="b5714-137">下面的代码示例将 <xref:System.Reflection.AssemblyKeyFileAttribute> 属性用于名为 keyfile.snk 的密钥文件（位于编译程序集的目录中）  。</span><span class="sxs-lookup"><span data-stu-id="b5714-137">The following example uses the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute with a key file called *keyfile.snk*, which is located in the directory where the assembly is compiled.</span></span>  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

<span data-ttu-id="b5714-138">在编译源文件时，也可以延迟为程序集签名。</span><span class="sxs-lookup"><span data-stu-id="b5714-138">You can also delay sign an assembly when compiling your source file.</span></span> <span data-ttu-id="b5714-139">有关详细信息，请参阅[延迟为程序集签名](delay-sign.md)。</span><span class="sxs-lookup"><span data-stu-id="b5714-139">For more information, see [Delay-sign an assembly](delay-sign.md).</span></span>  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a><span data-ttu-id="b5714-140">使用编译器为程序集签署强名称</span><span class="sxs-lookup"><span data-stu-id="b5714-140">Sign an assembly with a strong name by using the compiler</span></span>  

<span data-ttu-id="b5714-141">使用 C# 和 Visual Basic 中的 `/keyfile` 或 `/delaysign` 编译器选项，或使用 C++ 中的 `/KEYFILE` 或 `/DELAYSIGN` 链接器选项编译源代码文件。</span><span class="sxs-lookup"><span data-stu-id="b5714-141">Compile your source code file or files with the `/keyfile` or `/delaysign` compiler option in C# and Visual Basic, or the `/KEYFILE` or `/DELAYSIGN` linker option in C++.</span></span> <span data-ttu-id="b5714-142">在选项名称后，添加冒号和密钥文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b5714-142">After the option name, add a colon and the name of the key file.</span></span> <span data-ttu-id="b5714-143">使用命令行编译器时，你可以将密钥文件复制到包含源代码文件的目录中。</span><span class="sxs-lookup"><span data-stu-id="b5714-143">When using command-line compilers, you can copy the key file to the directory that contains your source code files.</span></span>  

<span data-ttu-id="b5714-144">有关延迟签名的信息，请参阅[延迟为程序集签名](delay-sign.md)。</span><span class="sxs-lookup"><span data-stu-id="b5714-144">For information on delay signing, see [Delay-sign an assembly](delay-sign.md).</span></span>  

<span data-ttu-id="b5714-145">下面的示例使用 C# 编译器并借助密钥文件 sgKey.snk 为程序集 UtilityLibrary.dll 签署强名称   。</span><span class="sxs-lookup"><span data-stu-id="b5714-145">The following example uses the C# compiler and signs the assembly *UtilityLibrary.dll* with a strong name by using the key file *sgKey.snk*.</span></span>  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a><span data-ttu-id="b5714-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5714-146">See also</span></span>

- [<span data-ttu-id="b5714-147">创建和使用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="b5714-147">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="b5714-148">如何：创建公钥/私钥对</span><span class="sxs-lookup"><span data-stu-id="b5714-148">How to: Create a public-private key pair</span></span>](create-public-private-key-pair.md)
- [<span data-ttu-id="b5714-149">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="b5714-149">Al.exe (Assembly Linker)</span></span>](../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="b5714-150">延迟为程序集签名</span><span class="sxs-lookup"><span data-stu-id="b5714-150">Delay-sign an assembly</span></span>](delay-sign.md)
- [<span data-ttu-id="b5714-151">管理程序集和清单签名</span><span class="sxs-lookup"><span data-stu-id="b5714-151">Manage assembly and manifest signing</span></span>](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [<span data-ttu-id="b5714-152">项目设计器的“签名”页</span><span class="sxs-lookup"><span data-stu-id="b5714-152">Signing page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
