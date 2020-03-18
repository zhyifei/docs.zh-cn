---
ms.openlocfilehash: 16ee73bfc0ab33b04ea3e2fa6d0eec521a9b8634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78967848"
---
### <a name="resource-manifest-file-names"></a>资源清单文件名

从 .NET Core 3.0 开始，生成的资源清单文件名已更改。

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="change-description"></a>更改描述

在 .NET Core 3.0 之前，当为 MSBuild 项目文件中的资源 (.resx) 文件设置了 [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) 元数据时，生成的清单名称为 Namespace.Classname.resources   。 当未设置 [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) 时，生成的清单名称为 Namespace.Classname.FolderPathRelativeToRoot.Culture.resources  。

从 .NET Core 3.0 开始，当 .resx 文件与同名的源文件位于同一位置（例如，在 Windows 窗体应用中）时，将从源文件中第一个类型的完整名称生成资源清单名称  。 例如，如果 Type.cs 与 Type.resx 位于同一位置，则生成的清单名称为 Namespace.Classname.resources    。 但是，如果修改了 .resx  文件的 `EmbeddedResource` 属性上的任何属性，则生成的清单文件名可能不同：

- 如果设置了 `EmbeddedResource` 属性上的 `LogicalName` 属性，则该值将用作资源清单文件名。

  示例：

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  **生成的资源清单文件名**：SomeName.resources（无论 .resx 文件名、区域性或任何其他元数据为何）   。

- 如果未设置 `LogicalName`，但设置了 `EmbeddedResource` 属性上的 `ManifestResourceName` 属性，则与文件扩展名 .resources 结合使用的值将用作资源清单文件名  。

  示例：

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  **生成的资源清单文件名**：SomeName.resources 或 SomeName.fr-FR.resources   。

- 如果前面的规则不适用，并且 `EmbeddedResource` 元素上的 `DependentUpon` 属性设置为源文件，则源文件中第一个类的类型名称将用于资源清单文件名。 更具体地说，生成的文件名为 Namespace.Classname\[.Culture].resources  。

  示例：

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  **生成的资源清单文件名**：Namespace.Classname.resources 或 Namespace.Classname.fr-FR.resources（其中 `Namespace.Classname` 是 MyTypes.cs 中第一个类的名称）    。

- 如果前面的规则不适用，`EmbeddedResourceUseDependentUponConvention` 为 `true`（.NET Core 的默认值），并且源文件与具有相同的基文件名的 .resx 文件位于同一位置，则 .resx 文件将依赖于匹配的源文件，并且生成的名称与上一个规则中的名称相同   。 这是 .NET Core 项目的“默认设置”规则。
  
  示例：
  
  MyTypes.cs  和 MyTypes.resx  或 MyTypes.fr-FR.resx  文件存在于同一文件夹中。
  
  **生成的资源清单文件名**：Namespace.Classname.resources 或 Namespace.Classname.fr-FR.resources（其中 `Namespace.Classname` 是 MyTypes.cs 中第一个类的名称）    。

- 如果前面的规则均不适用，则生成的资源清单文件名为 RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources  。 相对路径是 `EmbeddedResource` 元素的 `Link` 属性的值（如果已设置）。 否则，相对路径是 `EmbeddedResource` 元素的 `Identity` 属性的值。 在 Visual Studio 中，这是从项目根目录到解决方案资源管理器中的文件的路径。

#### <a name="recommended-action"></a>建议操作

如果你对生成的清单名称不满意，则可以：

- 根据前面所述的命名规则之一修改资源文件元数据。

- 将 `EmbeddedResourceUseDependentUponConvention` 设置为项目文件中的 `false`，以选择完全禁用新约定：

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > 如果存在 `LogicalName` 或 `ManifestResourceName` 属性，则它们的值仍将用于生成的文件名。

#### <a name="category"></a>类别

MSBuild

#### <a name="affected-apis"></a>受影响的 API

不可用
