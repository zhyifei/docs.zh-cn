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
# <a name="how-to-create-a-publisher-policy"></a>如何：创建发行者策略

程序集的供应商可以声明应用程序应使用较新版本的程序集，通过将发布者策略文件与升级的程序集一起。 发布者策略文件指定程序集重定向和代码库设置，并使用与应用程序配置文件相同的格式。 发布者策略文件编译到程序集中并放置在全局程序集缓存中。

创建发布者策略涉及三个步骤：

1. 创建发布者策略文件。

2. 创建发布者策略程序集。

3. 将发布者策略程序集添加到全局程序集缓存。

发布者策略的架构在[重定向程序集版本](redirect-assembly-versions.md)中描述。 下面的示例显示一个发布者策略文件，该文件将一`myAssembly`个版本重定向到另一个版本。

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

要了解如何指定代码库，请参阅[指定程序集的位置](specify-assembly-location.md)。

## <a name="creating-the-publisher-policy-assembly"></a>创建发布者策略程序集

使用[程序集链接器 （Al.exe）](../tools/al-exe-assembly-linker.md)创建发布者策略程序集。

#### <a name="to-create-a-publisher-policy-assembly"></a>创建发布者策略程序集

在命令提示符处键入以下命令：

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

在此命令中：

- 参数`publisherPolicyFile`是发布者策略文件的名称。

- 该`publisherPolicyAssemblyFile`参数是此命令产生的发布者策略程序集的名称。 程序集文件名必须遵循以下格式：

  "策略.主要编号.次要编号.mainAssemblyname.dll"

- 参数`keyPairFile`是包含密钥对的文件的名称。 您必须使用相同的密钥对对程序集和发布者策略程序集进行签名。

- 参数`processorArchitecture`标识处理器特定程序集的目标平台。

  > [!NOTE]
  > 从 .NET 框架 2.0 开始，可以定位特定处理器体系结构。

从 .NET 框架 2.0 开始，可以定位特定处理器体系结构。 以下命令创建一个发布者策略程序集`policy.1.0.myAssembly`，该程序集从称为的`pub.config`发布者策略文件调用，使用`sgKey.snk`文件中的密钥对向程序集分配强名称，并指定程序集以 x86 处理器体系结构为目标。

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

发布者策略程序集必须与它所应用的程序集的处理器体系结构匹配。 因此，如果程序集的值<xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A>为<xref:System.Reflection.ProcessorArchitecture.MSIL>`/platform:anycpu` 您必须为每个特定于处理器的程序集提供单独的发布者策略程序集。

此规则的结果是，为了更改程序集的处理器体系结构，必须更改版本号的主要或次要组件，以便可以使用正确的处理器体系结构提供新的发布者策略程序集。 一旦程序集具有不同的处理器体系结构，旧的发布者策略程序集将无法为程序集提供服务。

另一个后果是，版本 2.0 链接器不能用于为使用早期版本的 .NET Framework 编译的程序集创建发布者策略程序集，因为它始终指定处理器体系结构。

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>将发布者策略程序集添加到全局程序集缓存

使用[全局程序集缓存工具 （Gacutil.exe）](../tools/gacutil-exe-gac-tool.md)将发布者策略程序集添加到全局程序集缓存。

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>将发布者策略程序集添加到全局程序集缓存

在命令提示符处键入以下命令：

```console
gacutil /i publisherPolicyAssemblyFile
```

以下命令添加到`policy.1.0.myAssembly.dll`全局程序集缓存。

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> 除非`/link`参数中指定的原始发布者策略文件与程序集位于同一目录中，否则无法将发布者策略程序集添加到全局程序集缓存中。

## <a name="see-also"></a>另请参阅

- [使用程序集编程](../../standard/assembly/index.md)
- [运行时如何定位程序集](../deployment/how-the-runtime-locates-assemblies.md)
- [使用配置文件配置应用](index.md)
- [运行时设置架构](./file-schema/runtime/index.md)
- [配置文件架构](./file-schema/index.md)
- [重定向程序集版本](redirect-assembly-versions.md)
