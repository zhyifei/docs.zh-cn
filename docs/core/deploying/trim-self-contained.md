---
title: 剪裁独立应用程序
description: 了解如何剪裁独立应用以减小其大小。 .NET Core 将运行时与独立发布的应用捆绑在一起，通常包含比所需更多的运行时。
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242892"
---
# <a name="trim-self-contained-deployments-and-executables"></a>剪裁独立部署和可执行文件

当发布独立应用程序时，.NET Core 运行时会与该应用程序捆绑在一起。 此捆绑包向打包的应用程序添加了大量内容。 在涉及到应用程序部署时，大小通常是一个重要因素。 使包应用程序的大小尽可能小通常是应用程序开发者的目标。

根据应用程序的复杂性，运行应用程序只需要运行时的子集。 不需要这些未使用的运行时部分，可以从打包的应用程序中进行剪裁。

剪裁功能的工作方式是检查应用程序二进制文件，以发现和生成所需运行时程序集的关系图。 未引用的其余运行时程序集会被排除。

> [!NOTE]
> 剪裁是 .NET Core 3.1 中的实验性功能，只能用于独立发布的应用程序  。

## <a name="prevent-assemblies-from-being-trimmed"></a>防止剪裁程序集

在某些情况下，剪裁功能无法检测到引用。 例如，当应用程序或应用程序引用的库在运行时程序集上使用反射时，都不会直接引用该程序集。 剪裁不知道这些间接引用，并将从已发布文件夹中排除库。

当代码通过反射间接引用程序集时，可以防止使用 `<TrimmerRootAssembly>` 设置剪裁该程序集。 下面的示例演示如何防止剪裁名为 `System.Security` 程序集的程序集：

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a>剪裁应用 - CLI

使用 [dotnet publish](../tools/dotnet-publish.md) 命令剪裁应用程序。 发布应用时，请设定以下三个设置：

- 发布为自包含：`--self-contained true`
- 禁用单个文件发布：`-p:PublishSingleFile=false`
- 启用剪裁：`p:PublishTrimmed=true`

以下示例将 Windows 10 应用发布为自包含，并剪裁输出。

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

有关详细信息，请参阅[使用 .NET Core CLI 发布 .NET Core 应用](deploy-with-cli.md)。

## <a name="trim-your-app---visual-studio"></a>剪裁应用 - Visual Studio

Visual Studio 创建可重用的发布配置文件，用于控制应用程序的发布方式。

01. 在“解决方案资源管理器”窗格中，右键单击要发布的项目  。 选择“发布…”  。

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="解决方案资源管理器，其中右键单击菜单突出显示了“发布”选项。":::

    如果还没有发布配置文件，请按照说明创建一个并选择“文件夹”目标类型  。

01. 选择“编辑”  。

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="带有“编辑”按钮的 Visual Studio 发布配置文件。":::

01. 在“配置文件设置”对话框中，设置以下选项  ：

    - 将“部署模式”设置为“自包含”   。
    - 将“目标运行时”设置为要发布到的平台  。
    - 选择“剪裁未使用的程序集(预览版)”  。

    选择“保存”保存设置并返回到“发布”对话框   。

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="“配置文件设置”对话框，其中突出显示了“部署模式”、“目标运行时”和“剪裁未使用的程序集”选项。":::

01. 选择“发布”以发布剪裁过的应用  。

有关详细信息，请参阅[使用 Visual Studio 发布 .NET Core 应用](deploy-with-vs.md)。

## <a name="trim-your-app---visual-studio-for-mac"></a>剪裁应用 - Visual Studio for Mac

Visual Studio for Mac 不提供在发布期间剪裁应用的选项。 你需要按照[剪裁应用 - CLI](#trim-your-app---cli) 部分的说明手动发布。 有关详细信息，请参阅[使用 .NET Core CLI 发布 .NET Core 应用](deploy-with-cli.md)。

## <a name="see-also"></a>请参阅

- [.NET Core 应用程序部署](index.md)。
- [使用 .NET Core CLI 发布 .NET Core 应用](deploy-with-cli.md)。
- [使用 Visual Studio 发布 .NET Core 应用](deploy-with-vs.md)。
- [dotnet publish 命令](../tools/dotnet-publish.md)。
