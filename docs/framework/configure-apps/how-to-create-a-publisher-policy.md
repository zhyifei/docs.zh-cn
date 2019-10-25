---
title: 如何：创建发行者策略
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 608918828bf72369a1bd48e2391e2423078e9df0
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846839"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="7b7e8-102">如何：创建发行者策略</span><span class="sxs-lookup"><span data-stu-id="7b7e8-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="7b7e8-103">程序集的供应商可以通过包括发布服务器策略文件和已升级的程序集，指出应用程序应使用较新版本的程序集。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="7b7e8-104">发行者策略文件指定程序集重定向和基本代码设置，并使用与应用程序配置文件相同的格式。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="7b7e8-105">发行者策略文件编译到一个程序集中并置于全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="7b7e8-106">创建发布者策略涉及三个步骤：</span><span class="sxs-lookup"><span data-stu-id="7b7e8-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="7b7e8-107">创建发布者策略文件。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="7b7e8-108">创建发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="7b7e8-109">将发行者策略程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="7b7e8-110">[重定向程序集版本](redirect-assembly-versions.md)中介绍了发行者策略的架构。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="7b7e8-111">下面的示例演示一个发行者策略文件，该文件将一个 `myAssembly` 版本重定向到另一个版本。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
       <dependentAssembly>
         <assemblyIdentity name="myAssembly"
                           publicKeyToken="32ab4ba45e0a69a1"
                           culture="en-us" />
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->
         <bindingRedirect oldVersion="1.0.0.0"
                          newVersion="2.0.0.0"/>
       </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

<span data-ttu-id="7b7e8-112">若要了解如何指定基本代码，请参阅[指定程序集的位置](specify-assembly-location.md)。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="7b7e8-113">创建发行者策略程序集</span><span class="sxs-lookup"><span data-stu-id="7b7e8-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="7b7e8-114">使用[程序集链接器（al.exe）](../tools/al-exe-assembly-linker.md)来创建发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="7b7e8-115">创建发行者策略程序集</span><span class="sxs-lookup"><span data-stu-id="7b7e8-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="7b7e8-116">在命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b7e8-116">Type the following command at the command prompt:</span></span>

<span data-ttu-id="7b7e8-117">**al/link：** *publisherPolicyFile* **/Out：** *publisherPolicyAssemblyFile* **/keyfile：** *keyPairFile* **/platform：** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="7b7e8-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>

<span data-ttu-id="7b7e8-118">在此命令中：</span><span class="sxs-lookup"><span data-stu-id="7b7e8-118">In this command:</span></span>

- <span data-ttu-id="7b7e8-119">*PublisherPolicyFile*参数是发行者策略文件的名称。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="7b7e8-120">*PublisherPolicyAssemblyFile*参数是通过此命令生成的发行者策略程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="7b7e8-121">程序集文件名必须采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="7b7e8-121">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="7b7e8-122">**政策.**</span><span class="sxs-lookup"><span data-stu-id="7b7e8-122">**policy.**</span></span> <span data-ttu-id="7b7e8-123">*majorNumber* **。**</span><span class="sxs-lookup"><span data-stu-id="7b7e8-123">*majorNumber* **.**</span></span> <span data-ttu-id="7b7e8-124">*minorNumber* **。**</span><span class="sxs-lookup"><span data-stu-id="7b7e8-124">*minorNumber* **.**</span></span> <span data-ttu-id="7b7e8-125">*mainAssemblyName*</span><span class="sxs-lookup"><span data-stu-id="7b7e8-125">*mainAssemblyName* **.dll**</span></span>

- <span data-ttu-id="7b7e8-126">*KeyPairFile*参数是包含密钥对的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="7b7e8-127">必须用相同的密钥对对程序集和发行者策略程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="7b7e8-128">*ProcessorArchitecture*参数标识特定于处理器的程序集的目标平台。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7b7e8-129">从 .NET Framework 2.0 开始，可以获得特定处理器体系结构的目标功能。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-129">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="7b7e8-130">从 .NET Framework 2.0 开始，可以获得特定处理器体系结构的目标功能。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-130">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="7b7e8-131">下面的命令从名为 `pub.config`的发行者策略文件中创建名为 `policy.1.0.myAssembly` 的发行者策略程序集，并使用 `sgKey.snk` 文件中的密钥对将强名称分配给程序集，并指定该程序集面向 x86 处理器种.</span><span class="sxs-lookup"><span data-stu-id="7b7e8-131">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="7b7e8-132">发行者策略程序集必须与它所应用到的程序集的处理器体系结构匹配。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-132">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="7b7e8-133">因此，如果程序集的 <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> 值为 <xref:System.Reflection.ProcessorArchitecture.MSIL>，则必须使用 `/platform:anycpu`创建该程序集的发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-133">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="7b7e8-134">必须为每个处理器特定的程序集提供单独的发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-134">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="7b7e8-135">此规则的结果是，若要更改程序集的处理器体系结构，必须更改版本号的主要或次要组件，以便可以使用正确的处理器体系结构提供新的发行者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-135">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="7b7e8-136">如果程序集具有不同的处理器体系结构，则旧的发行者策略程序集无法为程序集提供服务。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-136">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="7b7e8-137">另一个结果是版本2.0 链接器无法用于为使用早期版本的 .NET Framework 编译的程序集创建发行者策略程序集，因为它始终指定处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-137">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="7b7e8-138">将发行者策略程序集添加到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="7b7e8-138">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="7b7e8-139">使用[全局程序集缓存工具（gacutil.exe）](../tools/gacutil-exe-gac-tool.md)将发行者策略程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-139">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="7b7e8-140">将发行者策略程序集添加到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="7b7e8-140">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="7b7e8-141">在命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b7e8-141">Type the following command at the command prompt:</span></span>

<span data-ttu-id="7b7e8-142">**gacutil.exe/I**  *publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="7b7e8-142">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>

<span data-ttu-id="7b7e8-143">以下命令将 `policy.1.0.myAssembly.dll` 添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-143">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="7b7e8-144">发行者策略程序集不能添加到全局程序集缓存，除非原始发布服务器策略文件与程序集位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="7b7e8-144">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b7e8-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b7e8-145">See also</span></span>

- [<span data-ttu-id="7b7e8-146">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="7b7e8-146">Programming with Assemblies</span></span>](../../standard/assembly/program.md)
- [<span data-ttu-id="7b7e8-147">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="7b7e8-147">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="7b7e8-148">使用配置文件配置应用程序</span><span class="sxs-lookup"><span data-stu-id="7b7e8-148">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="7b7e8-149">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="7b7e8-149">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="7b7e8-150">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="7b7e8-150">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="7b7e8-151">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="7b7e8-151">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
