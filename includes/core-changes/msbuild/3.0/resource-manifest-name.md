---
ms.openlocfilehash: 276268d31670b5e7dcd0ae9c0b7a61c3c38ca663
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451874"
---
### <a name="resource-manifest-file-names"></a><span data-ttu-id="a82bb-101">资源清单文件名</span><span class="sxs-lookup"><span data-stu-id="a82bb-101">Resource manifest file names</span></span>

<span data-ttu-id="a82bb-102">从 .NET Core 3.0 开始，生成的资源清单文件名已更改。</span><span class="sxs-lookup"><span data-stu-id="a82bb-102">Starting in .NET Core 3.0, the generated resource manifest file name has changed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a82bb-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="a82bb-103">Version introduced</span></span>

<span data-ttu-id="a82bb-104">3.0</span><span class="sxs-lookup"><span data-stu-id="a82bb-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="a82bb-105">更改描述</span><span class="sxs-lookup"><span data-stu-id="a82bb-105">Change description</span></span>

<span data-ttu-id="a82bb-106">在 .NET Core 3.0 之前，当为 MSBuild 项目文件中的资源 (.resx) 文件设置了 [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) 元数据时，生成的清单名称为 Namespace.Classname.resources   。</span><span class="sxs-lookup"><span data-stu-id="a82bb-106">Prior to .NET Core 3.0, when [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) metadata was set for a resource (*.resx*) file in the MSBuild project file, the generated manifest name was *Namespace.Classname.resources*.</span></span> <span data-ttu-id="a82bb-107">当未设置 [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) 时，生成的清单名称为 Namespace.Classname.FolderPathRelativeToRoot.Culture.resources  。</span><span class="sxs-lookup"><span data-stu-id="a82bb-107">When [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) was not set, the generated manifest name was *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span></span>

<span data-ttu-id="a82bb-108">从 .NET Core 3.0 开始，当 .resx 文件与同名的源文件位于同一位置（例如，在 Windows 窗体应用中）时，将从源文件中第一个类型的完整名称生成资源清单名称  。</span><span class="sxs-lookup"><span data-stu-id="a82bb-108">Starting in .NET Core 3.0, when a *.resx* file is colocated with a source file of the same name, for example, in Windows Forms apps, the resource manifest name is generated from the full name of the first type in the source file.</span></span> <span data-ttu-id="a82bb-109">例如，如果 Type.cs 与 Type.resx 位于同一位置，则生成的清单名称为 Namespace.Classname.resources    。</span><span class="sxs-lookup"><span data-stu-id="a82bb-109">For example, if *Type.cs* is colocated with *Type.resx*, the generated manifest name is *Namespace.Classname.resources*.</span></span> <span data-ttu-id="a82bb-110">但是，如果修改了 .resx  文件的 `EmbeddedResource` 属性上的任何属性，则生成的清单文件名可能不同：</span><span class="sxs-lookup"><span data-stu-id="a82bb-110">However, if you modify any of the attributes on the `EmbeddedResource` property for the *.resx* file, the generated manifest file name may be different:</span></span>

- <span data-ttu-id="a82bb-111">如果设置了 `EmbeddedResource` 属性上的 `LogicalName` 属性，则该值将用作资源清单文件名。</span><span class="sxs-lookup"><span data-stu-id="a82bb-111">If the `LogicalName` attribute on the `EmbeddedResource` property is set, that value is used as the resource manifest file name.</span></span>

  <span data-ttu-id="a82bb-112">示例：</span><span class="sxs-lookup"><span data-stu-id="a82bb-112">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  <span data-ttu-id="a82bb-113">**生成的资源清单文件名**：SomeName.resources（无论 .resx 文件名、区域性或任何其他元数据为何）   。</span><span class="sxs-lookup"><span data-stu-id="a82bb-113">**Generated resource manifest file name**: *SomeName.resources* (regardless of the *.resx* file name or culture or any other metadata).</span></span>

- <span data-ttu-id="a82bb-114">如果未设置 `LogicalName`，但设置了 `EmbeddedResource` 属性上的 `ManifestResourceName` 属性，则与文件扩展名 .resources 结合使用的值将用作资源清单文件名  。</span><span class="sxs-lookup"><span data-stu-id="a82bb-114">If `LogicalName` is not set, but the `ManifestResourceName` attribute on the `EmbeddedResource` property is set, its value, combined with the file extension *.resources*, is used as the resource manifest file name.</span></span>

  <span data-ttu-id="a82bb-115">示例：</span><span class="sxs-lookup"><span data-stu-id="a82bb-115">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  <span data-ttu-id="a82bb-116">**生成的资源清单文件名**：SomeName.resources 或 SomeName.fr-FR.resources   。</span><span class="sxs-lookup"><span data-stu-id="a82bb-116">**Generated resource manifest file name**: *SomeName.resources* or *SomeName.fr-FR.resources*.</span></span>

- <span data-ttu-id="a82bb-117">如果前面的规则不适用，并且 `EmbeddedResource` 元素上的 `DependentUpon` 属性设置为源文件，则源文件中第一个类的类型名称将用于资源清单文件名。</span><span class="sxs-lookup"><span data-stu-id="a82bb-117">If the previous rules don't apply, and the `DependentUpon` attribute on the `EmbeddedResource` element is set to a source file, the type name of the first class in the source file is used in the resource manifest file name.</span></span> <span data-ttu-id="a82bb-118">更具体地说，生成的文件名为 Namespace.Classname\[.Culture].resources  。</span><span class="sxs-lookup"><span data-stu-id="a82bb-118">More specifically, the generated file name is *Namespace.Classname\[.Culture].resources*.</span></span>

  <span data-ttu-id="a82bb-119">示例：</span><span class="sxs-lookup"><span data-stu-id="a82bb-119">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  <span data-ttu-id="a82bb-120">**生成的资源清单文件名**：Namespace.Classname.resources 或 Namespace.Classname.fr-FR.resources（其中 `Namespace.Classname` 是 MyTypes.cs 中第一个类的名称）    。</span><span class="sxs-lookup"><span data-stu-id="a82bb-120">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="a82bb-121">如果前面的规则不适用，`EmbeddedResourceUseDependentUponConvention` 为 `true`（.NET Core 的默认值），并且源文件与具有相同的基文件名的 .resx 文件位于同一位置，则 .resx 文件将依赖于匹配的源文件，并且生成的名称与上一个规则中的名称相同   。</span><span class="sxs-lookup"><span data-stu-id="a82bb-121">If the previous rules don't apply, `EmbeddedResourceUseDependentUponConvention` is `true` (the default for .NET Core), and there's a source file colocated with a *.resx* file that has the same base file name, the *.resx* file is made dependent upon the matching source file, and the generated name is the same as in the previous rule.</span></span> <span data-ttu-id="a82bb-122">这是 .NET Core 项目的“默认设置”规则。</span><span class="sxs-lookup"><span data-stu-id="a82bb-122">This is the "default settings" rule for .NET Core projects.</span></span>
  
  <span data-ttu-id="a82bb-123">示例：</span><span class="sxs-lookup"><span data-stu-id="a82bb-123">Examples:</span></span>
  
  <span data-ttu-id="a82bb-124">MyTypes.cs  和 MyTypes.resx  或 MyTypes.fr-FR.resx  文件存在于同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a82bb-124">Files *MyTypes.cs* and *MyTypes.resx* or *MyTypes.fr-FR.resx* exist in the same folder.</span></span>
  
  <span data-ttu-id="a82bb-125">**生成的资源清单文件名**：Namespace.Classname.resources 或 Namespace.Classname.fr-FR.resources（其中 `Namespace.Classname` 是 MyTypes.cs 中第一个类的名称）    。</span><span class="sxs-lookup"><span data-stu-id="a82bb-125">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>
    
- <span data-ttu-id="a82bb-126">如果前面的规则均不适用，则生成的资源清单文件名为 RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources  。</span><span class="sxs-lookup"><span data-stu-id="a82bb-126">If none of the previous rules apply, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="a82bb-127">相对路径是 `EmbeddedResource` 元素的 `Link` 属性的值（如果已设置）。</span><span class="sxs-lookup"><span data-stu-id="a82bb-127">The relative path is the value of the `Link` attribute of the `EmbeddedResource` element if it's set.</span></span> <span data-ttu-id="a82bb-128">否则，相对路径是 `EmbeddedResource` 元素的 `Identity` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="a82bb-128">Otherwise, the relative path is the value of the `Identity` attribute of the `EmbeddedResource` element.</span></span> <span data-ttu-id="a82bb-129">在 Visual Studio 中，这是从项目根目录到解决方案资源管理器中的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a82bb-129">In Visual Studio, this is the path from the project root to the file in Solution Explorer.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a82bb-130">建议操作</span><span class="sxs-lookup"><span data-stu-id="a82bb-130">Recommended action</span></span>

<span data-ttu-id="a82bb-131">如果你对生成的清单名称不满意，则可以：</span><span class="sxs-lookup"><span data-stu-id="a82bb-131">If you're unsatisfied with the generated manifest names, you can:</span></span>

- <span data-ttu-id="a82bb-132">根据前面所述的命名规则之一修改资源文件元数据。</span><span class="sxs-lookup"><span data-stu-id="a82bb-132">Modify your resource file metadata according to one of the previously described naming rules.</span></span>

- <span data-ttu-id="a82bb-133">将 `EmbeddedResourceUseDependentUponConvention` 设置为项目文件中的 `false`，以选择完全禁用新约定：</span><span class="sxs-lookup"><span data-stu-id="a82bb-133">Set `EmbeddedResourceUseDependentUponConvention` to `false` in your project file to opt out of the new convention entirely:</span></span>

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > <span data-ttu-id="a82bb-134">如果存在 `LogicalName` 或 `ManifestResourceName` 属性，则它们的值仍将用于生成的文件名。</span><span class="sxs-lookup"><span data-stu-id="a82bb-134">If the `LogicalName` or `ManifestResourceName` attributes are present, their values will still be used for the generated file name.</span></span>

#### <a name="category"></a><span data-ttu-id="a82bb-135">类别</span><span class="sxs-lookup"><span data-stu-id="a82bb-135">Category</span></span>

<span data-ttu-id="a82bb-136">MSBuild</span><span class="sxs-lookup"><span data-stu-id="a82bb-136">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a82bb-137">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a82bb-137">Affected APIs</span></span>

<span data-ttu-id="a82bb-138">不可用</span><span class="sxs-lookup"><span data-stu-id="a82bb-138">N/A</span></span>
