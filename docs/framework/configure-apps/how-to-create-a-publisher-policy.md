---
title: 如何：创建发行者策略
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646060"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="df632-102">如何：创建发行者策略</span><span class="sxs-lookup"><span data-stu-id="df632-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="df632-103">程序集的供应商可以声明应用程序应使用较新版本的程序集，通过将发布者策略文件与升级的程序集一起。</span><span class="sxs-lookup"><span data-stu-id="df632-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="df632-104">发布者策略文件指定程序集重定向和代码库设置，并使用与应用程序配置文件相同的格式。</span><span class="sxs-lookup"><span data-stu-id="df632-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="df632-105">发布者策略文件编译到程序集中并放置在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="df632-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="df632-106">创建发布者策略涉及三个步骤：</span><span class="sxs-lookup"><span data-stu-id="df632-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="df632-107">创建发布者策略文件。</span><span class="sxs-lookup"><span data-stu-id="df632-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="df632-108">创建发布者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="df632-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="df632-109">将发布者策略程序集添加到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="df632-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="df632-110">发布者策略的架构在[重定向程序集版本](redirect-assembly-versions.md)中描述。</span><span class="sxs-lookup"><span data-stu-id="df632-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="df632-111">下面的示例显示一个发布者策略文件，该文件将一`myAssembly`个版本重定向到另一个版本。</span><span class="sxs-lookup"><span data-stu-id="df632-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="df632-112">要了解如何指定代码库，请参阅[指定程序集的位置](specify-assembly-location.md)。</span><span class="sxs-lookup"><span data-stu-id="df632-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="df632-113">创建发布者策略程序集</span><span class="sxs-lookup"><span data-stu-id="df632-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="df632-114">使用[程序集链接器 （Al.exe）](../tools/al-exe-assembly-linker.md)创建发布者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="df632-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="df632-115">创建发布者策略程序集</span><span class="sxs-lookup"><span data-stu-id="df632-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="df632-116">在命令提示符处键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="df632-116">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="df632-117">在此命令中：</span><span class="sxs-lookup"><span data-stu-id="df632-117">In this command:</span></span>

- <span data-ttu-id="df632-118">参数`publisherPolicyFile`是发布者策略文件的名称。</span><span class="sxs-lookup"><span data-stu-id="df632-118">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="df632-119">该`publisherPolicyAssemblyFile`参数是此命令产生的发布者策略程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="df632-119">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="df632-120">程序集文件名必须遵循以下格式：</span><span class="sxs-lookup"><span data-stu-id="df632-120">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="df632-121">"策略.主要编号.次要编号.mainAssemblyname.dll"</span><span class="sxs-lookup"><span data-stu-id="df632-121">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="df632-122">参数`keyPairFile`是包含密钥对的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="df632-122">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="df632-123">您必须使用相同的密钥对对程序集和发布者策略程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="df632-123">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="df632-124">参数`processorArchitecture`标识处理器特定程序集的目标平台。</span><span class="sxs-lookup"><span data-stu-id="df632-124">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="df632-125">从 .NET 框架 2.0 开始，可以定位特定处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="df632-125">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="df632-126">从 .NET 框架 2.0 开始，可以定位特定处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="df632-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="df632-127">以下命令创建一个发布者策略程序集`policy.1.0.myAssembly`，该程序集从称为的`pub.config`发布者策略文件调用，使用`sgKey.snk`文件中的密钥对向程序集分配强名称，并指定程序集以 x86 处理器体系结构为目标。</span><span class="sxs-lookup"><span data-stu-id="df632-127">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="df632-128">发布者策略程序集必须与它所应用的程序集的处理器体系结构匹配。</span><span class="sxs-lookup"><span data-stu-id="df632-128">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="df632-129">因此，如果程序集的值<xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A>为<xref:System.Reflection.ProcessorArchitecture.MSIL>`/platform:anycpu`</span><span class="sxs-lookup"><span data-stu-id="df632-129">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="df632-130">您必须为每个特定于处理器的程序集提供单独的发布者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="df632-130">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="df632-131">此规则的结果是，为了更改程序集的处理器体系结构，必须更改版本号的主要或次要组件，以便可以使用正确的处理器体系结构提供新的发布者策略程序集。</span><span class="sxs-lookup"><span data-stu-id="df632-131">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="df632-132">一旦程序集具有不同的处理器体系结构，旧的发布者策略程序集将无法为程序集提供服务。</span><span class="sxs-lookup"><span data-stu-id="df632-132">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="df632-133">另一个后果是，版本 2.0 链接器不能用于为使用早期版本的 .NET Framework 编译的程序集创建发布者策略程序集，因为它始终指定处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="df632-133">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="df632-134">将发布者策略程序集添加到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="df632-134">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="df632-135">使用[全局程序集缓存工具 （Gacutil.exe）](../tools/gacutil-exe-gac-tool.md)将发布者策略程序集添加到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="df632-135">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="df632-136">将发布者策略程序集添加到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="df632-136">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="df632-137">在命令提示符处键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="df632-137">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="df632-138">以下命令添加到`policy.1.0.myAssembly.dll`全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="df632-138">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="df632-139">除非`/link`参数中指定的原始发布者策略文件与程序集位于同一目录中，否则无法将发布者策略程序集添加到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="df632-139">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="df632-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df632-140">See also</span></span>

- [<span data-ttu-id="df632-141">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="df632-141">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="df632-142">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="df632-142">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="df632-143">使用配置文件配置应用</span><span class="sxs-lookup"><span data-stu-id="df632-143">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="df632-144">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="df632-144">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="df632-145">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="df632-145">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="df632-146">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="df632-146">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
