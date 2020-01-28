---
title: 编译应用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], building
ms.assetid: a58696fd-bdad-4b55-9759-136dfdf8b91c
ms.openlocfilehash: 00c76dfcdcedc7ceaefaaae785368f8b343457a7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744763"
---
# <a name="compile-a-wpf-application"></a><span data-ttu-id="0227e-102">编译 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="0227e-102">Compile a WPF Application</span></span>

<span data-ttu-id="0227e-103">Windows Presentation Foundation （WPF）应用程序可以生成为 .NET Framework 可执行文件（.exe）、库（.dll）或这两种类型的程序集的组合。</span><span class="sxs-lookup"><span data-stu-id="0227e-103">Windows Presentation Foundation (WPF) applications can be built as .NET Framework executables (.exe), libraries (.dll), or a combination of both types of assemblies.</span></span> <span data-ttu-id="0227e-104">本主题介绍如何构建 WPF 应用程序，并介绍生成过程中的关键步骤。</span><span class="sxs-lookup"><span data-stu-id="0227e-104">This topic introduces how to build WPF applications and describes the key steps in the build process.</span></span>

<a name="Building_a_WPF_Application_using_Command_Line"></a>

## <a name="building-a-wpf-application"></a><span data-ttu-id="0227e-105">WPF 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="0227e-105">Building a WPF Application</span></span>

<span data-ttu-id="0227e-106">다음과 같은 방법으로 WPF 애플리케이션을 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-106">A WPF application can be compiled in the following ways:</span></span>

- <span data-ttu-id="0227e-107">명령줄.</span><span class="sxs-lookup"><span data-stu-id="0227e-107">Command-line.</span></span> <span data-ttu-id="0227e-108">애플리케이션에 코드(XAML 없음)와 애플리케이션 정의 파일만 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-108">The application must contain only code (no XAML) and an application definition file.</span></span> <span data-ttu-id="0227e-109">자세한 내용은 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) 또는 [명령줄에서 빌드(Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0227e-109">For more information, see [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Building from the Command Line (Visual Basic)](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

- <span data-ttu-id="0227e-110">MSBuild(Microsoft Build Engine).</span><span class="sxs-lookup"><span data-stu-id="0227e-110">Microsoft Build Engine (MSBuild).</span></span> <span data-ttu-id="0227e-111">애플리케이션에 코드 및 XAML 파일 외에 MSBuild 프로젝트 파일이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-111">In addition to the code and XAML files, the application must contain an MSBuild project file.</span></span> <span data-ttu-id="0227e-112">자세한 내용은 "MSBuild"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0227e-112">For more information, see "MSBuild".</span></span>

- <span data-ttu-id="0227e-113">보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-113">Visual Studio.</span></span> <span data-ttu-id="0227e-114">Visual Studio는 MSBuild를 사용하여 WPF 애플리케이션을 컴파일하고 UI를 만들기 위한 비주얼 디자이너를 포함하는 통합 개발 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-114">Visual Studio is an integrated development environment that compiles WPF applications with MSBuild and includes a visual designer for creating UI.</span></span> <span data-ttu-id="0227e-115">有关详细信息，请参阅[使用 Visual Studio 编写和管理代码](/visualstudio/ide/index-writing-code)和[在 Visual STUDIO 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="0227e-115">For more information, see [Write and manage code using Visual Studio](/visualstudio/ide/index-writing-code) and [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

<a name="The_Windows_Presentation_Foundation_Build_Pipeline"></a>

## <a name="wpf-build-pipeline"></a><span data-ttu-id="0227e-116">WPF 빌드 파이프라인</span><span class="sxs-lookup"><span data-stu-id="0227e-116">WPF Build Pipeline</span></span>

<span data-ttu-id="0227e-117">生成 WPF 项目时，将调用语言特定目标和特定于 WPF 的目标的组合。</span><span class="sxs-lookup"><span data-stu-id="0227e-117">When a WPF project is built, the combination of language-specific and WPF-specific targets are invoked.</span></span> <span data-ttu-id="0227e-118">이러한 대상을 실행 중인 프로세스를 빌드 파이프라인이라고 하며 주요 단계는 다음 그림에서와 같이 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-118">The process of executing these targets is called the build pipeline, and the key steps are illustrated by the following figure.</span></span>

<span data-ttu-id="0227e-119">![WPF 生成过程](./media/wpfbuildsystem-figure1.png "WPFBuildSystem_Figure1")</span><span class="sxs-lookup"><span data-stu-id="0227e-119">![WPF build process](./media/wpfbuildsystem-figure1.png "WPFBuildSystem_Figure1")</span></span>

<a name="Pre_Build_Initializations"></a>

### <a name="pre-build-initializations"></a><span data-ttu-id="0227e-120">빌드 전 초기화</span><span class="sxs-lookup"><span data-stu-id="0227e-120">Pre-Build Initializations</span></span>

<span data-ttu-id="0227e-121">在生成之前，MSBuild 确定重要工具和库的位置，包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="0227e-121">Before building, MSBuild determines the location of important tools and libraries, including the following:</span></span>

- <span data-ttu-id="0227e-122">.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="0227e-122">The .NET Framework.</span></span>

- <span data-ttu-id="0227e-123">Windows SDK 的目录。</span><span class="sxs-lookup"><span data-stu-id="0227e-123">The Windows SDK directories.</span></span>

- <span data-ttu-id="0227e-124">WPF 引用程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="0227e-124">The location of WPF reference assemblies.</span></span>

- <span data-ttu-id="0227e-125">어셈블리 검색 경로의 속성</span><span class="sxs-lookup"><span data-stu-id="0227e-125">The property for the assembly search paths.</span></span>

<span data-ttu-id="0227e-126">MSBuild 在其中搜索程序集的第一个位置是引用程序集目录（%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.0\\）。</span><span class="sxs-lookup"><span data-stu-id="0227e-126">The first location where MSBuild searches for assemblies is the reference assembly directory (%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.0\\).</span></span> <span data-ttu-id="0227e-127">이 단계에서 빌드 프로세스는 다양한 속성 및 항목 그룹을 초기화하고 필요한 정리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-127">During this step, the build process also initializes the various properties and item groups and performs any required cleanup work.</span></span>

<a name="Resolving_references"></a>

### <a name="resolving-references"></a><span data-ttu-id="0227e-128">참조 확인</span><span class="sxs-lookup"><span data-stu-id="0227e-128">Resolving References</span></span>

<span data-ttu-id="0227e-129">빌드 프로세스는 애플리케이션 프로젝트를 빌드하는 데 필요한 어셈블리를 찾아서 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-129">The build process locates and binds the assemblies required to build the application project.</span></span> <span data-ttu-id="0227e-130">이 논리는 `ResolveAssemblyReference` 작업에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-130">This logic is contained in the `ResolveAssemblyReference` task.</span></span> <span data-ttu-id="0227e-131">프로젝트 파일에서 `Reference`로 선언된 모든 어셈블리는 시스템에 이미 설치된 어셈블리의 메타데이터 및 검색 경로에 대한 정보와 함께 작업에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-131">All assemblies declared as `Reference` in the project file are provided to the task along with information on the search paths and metadata on assemblies already installed on the system.</span></span> <span data-ttu-id="0227e-132">该任务将查找程序集，并使用已安装的程序集的元数据来筛选出那些不需要显示在输出清单中的核心 WPF 程序集。</span><span class="sxs-lookup"><span data-stu-id="0227e-132">The task looks up assemblies and uses the installed assembly's metadata to filter out those core WPF assemblies that need not show up in the output manifests.</span></span> <span data-ttu-id="0227e-133">이 작업의 목적은 ClickOnce 매니페스트에서 중복되는 정보를 방지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-133">This is done to avoid redundant information in the ClickOnce manifests.</span></span> <span data-ttu-id="0227e-134">例如，由于 PresentationFramework 可被视为在和 WPF 上构建的应用程序的代表，并且由于在安装了 .NET Framework 的每台计算机上的同一位置都存在所有 WPF 程序集，因此无需包括所有有关清单中所有 .NET Framework 引用程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="0227e-134">For example, since PresentationFramework.dll can be considered representative of an application built on and for WPF, and since all WPF assemblies exist at the same location on every machine that has the .NET Framework installed, there's no need to include all information on all .NET Framework reference assemblies in the manifests.</span></span>

<a name="Markup_Compilation___Pass_1"></a>

### <a name="markup-compilationpass-1"></a><span data-ttu-id="0227e-135">태그 컴파일 - 패스 1</span><span class="sxs-lookup"><span data-stu-id="0227e-135">Markup Compilation—Pass 1</span></span>

<span data-ttu-id="0227e-136">在此步骤中，将对 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件进行分析和编译，使运行时不会花费时间分析 XML 和验证属性值。</span><span class="sxs-lookup"><span data-stu-id="0227e-136">In this step, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files are parsed and compiled so that the runtime does not spend time parsing XML and validating property values.</span></span> <span data-ttu-id="0227e-137">컴파일된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 사전 토큰화되어 있으므로 런타임 시 이 파일을 로드하면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 로드하는 것보다 훨씬 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-137">The compiled [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is pre-tokenized so that, at run time, loading it should be much faster than loading a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span>

<span data-ttu-id="0227e-138">이 단계에서 다음 작업은 `Page` 빌드 항목인 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 대해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-138">During this step, the following activities take place for every [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file that is a `Page` build item:</span></span>

1. <span data-ttu-id="0227e-139">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 태그 컴파일러에 의해 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-139">The [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is parsed by the markup compiler.</span></span>

2. <span data-ttu-id="0227e-140">컴파일된 표현은 해당 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 대해 만들어져서 obj\Release 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-140">A compiled representation is created for that [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and copied to the obj\Release folder.</span></span>

3. <span data-ttu-id="0227e-141">새 partial 클래스의 CodeDOM 표현이 만들어져서 obj\Release 폴더에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-141">A CodeDOM representation of a new partial class is created and copied to the obj\Release folder.</span></span>

<span data-ttu-id="0227e-142">또한 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 대해 언어별 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-142">In addition, a language-specific code file is generated for every [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="0227e-143">例如，对于 Visual Basic 项目中的 Page1 页，生成了 Page1. g.;对于C#项目中的 Page1 页，会生成 Page1.g.cs。</span><span class="sxs-lookup"><span data-stu-id="0227e-143">For example, for a Page1.xaml page in a Visual Basic project, a Page1.g.vb is generated; for a Page1.xaml page in a C# project, a Page1.g.cs is generated.</span></span> <span data-ttu-id="0227e-144">파일 이름에 ".g"가 있으면 파일이 태그 파일(예: `Page` 또는 `Window`)의 최상위 수준 요소에 대한 partial 클래스 선언을 포함하여 생성된 코드라는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-144">The ".g" in the file name indicates the file is generated code that has a partial class declaration for the top-level element of the markup file (such as `Page` or `Window`).</span></span> <span data-ttu-id="0227e-145">此类是用中C#的 `partial` 修饰符声明的（`Extends` 在 Visual Basic 中），以指示该类的其他声明（通常在代码隐藏文件 Page1.xaml.cs 中）。</span><span class="sxs-lookup"><span data-stu-id="0227e-145">The class is declared with the `partial` modifier in C# (`Extends` in Visual Basic) to indicate there is another declaration for the class elsewhere, usually in the code-behind file Page1.xaml.cs.</span></span>

<span data-ttu-id="0227e-146">分部类从适当的基类（如页面 <xref:System.Windows.Controls.Page>）进行扩展并实现 <xref:System.Windows.Markup.IComponentConnector?displayProperty=nameWithType> 接口。</span><span class="sxs-lookup"><span data-stu-id="0227e-146">The partial class extends from the appropriate base class (such as <xref:System.Windows.Controls.Page> for a page) and implements the <xref:System.Windows.Markup.IComponentConnector?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="0227e-147"><xref:System.Windows.Markup.IComponentConnector> 接口包含用于初始化组件并连接其内容中元素上的名称和事件的方法。</span><span class="sxs-lookup"><span data-stu-id="0227e-147">The <xref:System.Windows.Markup.IComponentConnector> interface has methods to initialize a component and connect names and events on elements in its content.</span></span> <span data-ttu-id="0227e-148">결과적으로 생성된 코드 파일에는 다음과 같은 메서드 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-148">Consequently, the generated code file has a method implementation like the following:</span></span>

```csharp
public void InitializeComponent() {
    if (_contentLoaded) {
        return;
    }
    _contentLoaded = true;
    System.Uri resourceLocater =
        new System.Uri(
            "window1.xaml",
            System.UriKind.RelativeOrAbsolute);
    System.Windows.Application.LoadComponent(this, resourceLocater);
}
```

```vb
Public Sub InitializeComponent() _

    If _contentLoaded Then
        Return
    End If

    _contentLoaded = True
    Dim resourceLocater As System.Uri = _
        New System.Uri("mainwindow.xaml", System.UriKind.Relative)

    System.Windows.Application.LoadComponent(Me, resourceLocater)

End Sub
```

<span data-ttu-id="0227e-149">默认情况下，标记编译在与 MSBuild 引擎相同的 <xref:System.AppDomain> 中运行。</span><span class="sxs-lookup"><span data-stu-id="0227e-149">By default, markup compilation runs in the same <xref:System.AppDomain> as the MSBuild engine.</span></span> <span data-ttu-id="0227e-150">따라서 성능이 크게 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-150">This provides significant performance gains.</span></span> <span data-ttu-id="0227e-151">이 동작은 `AlwaysCompileMarkupFilesInSeparateDomain` 속성을 통해 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-151">This behavior can be toggled with the `AlwaysCompileMarkupFilesInSeparateDomain` property.</span></span> <span data-ttu-id="0227e-152">此方法的优点是通过卸载单独的 <xref:System.AppDomain>卸载所有引用程序集。</span><span class="sxs-lookup"><span data-stu-id="0227e-152">This has the advantage of unloading all reference assemblies by unloading the separate <xref:System.AppDomain>.</span></span>

<a name="Pass_2_of_Markup_Compilation"></a>

### <a name="markup-compilationpass-2"></a><span data-ttu-id="0227e-153">태그 컴파일 - 패스 2</span><span class="sxs-lookup"><span data-stu-id="0227e-153">Markup Compilation—Pass 2</span></span>

<span data-ttu-id="0227e-154">일부 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 태그 컴파일의 패스 1에서 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-154">Not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages are compiled at during pass 1 of markup compilation.</span></span> <span data-ttu-id="0227e-155">이때 로컬로 정의된 형식 참조(동일한 프로젝트의 코드에서 정의된 형식에 대한 참조)가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 컴파일에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-155">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that have locally defined type references (references to types defined in code elsewhere in the same project) are exempt from compilation at this time.</span></span> <span data-ttu-id="0227e-156">이는 로컬로 정의된 형식이 소스에만 있어 아직 컴파일되지 않았기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-156">This is because those locally defined types exist only in source and have not yet been compiled.</span></span> <span data-ttu-id="0227e-157">이를 확인하기 위해 파서는 추론을 사용하여 태그 파일에서 `x:Name`과 같은 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-157">In order to determine this, the parser uses heuristics that involve looking for items such as `x:Name` in the markup file.</span></span> <span data-ttu-id="0227e-158">이러한 인스턴스를 찾은 경우 코드 파일이 컴파일될 때까지 해당 태그 파일의 컴파일이 연기되며 나중에 두 번째 태그 컴파일 패스가 이러한 파일을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-158">When such an instance is found, that markup file’s compilation is postponed until the code files have been compiled, after which, the second markup compilation pass processes these files.</span></span>

<a name="File_Classification"></a>

### <a name="file-classification"></a><span data-ttu-id="0227e-159">파일 분류</span><span class="sxs-lookup"><span data-stu-id="0227e-159">File Classification</span></span>

<span data-ttu-id="0227e-160">빌드 프로세스는 출력 파일을 배치할 애플리케이션 어셈블리를 기반으로 다른 리소스 그룹에 출력 파일을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-160">The build process puts output files into different resource groups based on which application assembly they will be placed in.</span></span> <span data-ttu-id="0227e-161">일반적으로 지역화되지 않은 애플리케이션에서 `Resource`로 표시된 모든 데이터 파일은 주 어셈블리(실행 파일 또는 라이브러리)에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-161">In a typical nonlocalized application, all data files marked as `Resource` are placed in the main assembly (executable or library).</span></span> <span data-ttu-id="0227e-162">프로젝트에서 `UICulture`가 설정된 경우 컴파일된 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 및 해당 리소스(특히 언어별로 표시된 리소스)가 위성 리소스 어셈블리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-162">When `UICulture` is set in the project, all compiled [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files and those resources specifically marked as language-specific are placed in the satellite resource assembly.</span></span> <span data-ttu-id="0227e-163">또한 모든 언어 중립 리소스는 주 어셈블리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-163">Furthermore, all language-neutral resources are placed in the main assembly.</span></span> <span data-ttu-id="0227e-164">빌드 프로세스의 이 단계에서 해당 사항이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-164">In this step of the build process, that determination is made.</span></span>

<span data-ttu-id="0227e-165">프로젝트 파일의 `ApplicationDefinition`, `Page` 및 `Resource` 빌드 작업은 `Localizable` 메타데이터(허용 가능한 값은 `true` 및 `false`)를 통해 보강할 수 있으며 이는 파일이 언어와 관련되었는지 또는 언어 중립적인지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-165">The `ApplicationDefinition`, `Page`, and `Resource` build actions in the project file can be augmented with the `Localizable` metadata (acceptable values are `true` and `false`), which dictates whether the file is language-specific or language-neutral.</span></span>

<a name="Core_Compilation"></a>

### <a name="core-compilation"></a><span data-ttu-id="0227e-166">핵심 컴파일</span><span class="sxs-lookup"><span data-stu-id="0227e-166">Core Compilation</span></span>

<span data-ttu-id="0227e-167">핵심 컴파일 단계에서는 코드 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-167">The core compile step involves compilation of code files.</span></span> <span data-ttu-id="0227e-168">이 작업은 언어별 대상 파일 Microsoft.CSharp.targets 및 Microsoft.VisualBasic.targets의 논리에 의해 오케스트레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-168">This is orchestrated by logic in the language-specific targets files Microsoft.CSharp.targets and Microsoft.VisualBasic.targets.</span></span> <span data-ttu-id="0227e-169">추론을 통해 태그 컴파일러의 단일 패스로 충분하다고 판단된 경우 주 어셈블리가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-169">If heuristics have determined that a single pass of the markup compiler is sufficient, then the main assembly is generated.</span></span> <span data-ttu-id="0227e-170">그러나 프로젝트에서 하나 이상의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 로컬로 정의된 형식에 대한 참조가 있는 경우 태그 컴파일의 두 번째 패스가 완료된 후 최종 애플리케이션 어셈블리가 만들어질 수 있도록 임시 .dll 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-170">However, if one or more [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files in the project have references to locally defined types, then a temporary .dll file is generated so the final application assemblies may be created after the second pass of markup compilation is complete.</span></span>

<a name="Manifest_generation"></a>

### <a name="manifest-generation"></a><span data-ttu-id="0227e-171">매니페스트 생성</span><span class="sxs-lookup"><span data-stu-id="0227e-171">Manifest Generation</span></span>

<span data-ttu-id="0227e-172">在生成过程结束时，所有应用程序程序集和内容文件都准备就绪后，将生成应用程序的 ClickOnce 清单。</span><span class="sxs-lookup"><span data-stu-id="0227e-172">At the end of the build process, after all the application assemblies and content files are ready, the ClickOnce manifests for the application are generated.</span></span>

<span data-ttu-id="0227e-173">배포 매니페스트 파일은 배포 모델, 즉 현재 버전, 업데이트 동작 및 게시자 ID를 디지털 시그니처와 함께 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-173">The deployment manifest file describes the deployment model: the current version, update behavior, and publisher identity along with digital signature.</span></span> <span data-ttu-id="0227e-174">이 매니페스트는 배포를 처리하는 관리자가 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-174">This manifest is intended to be authored by administrators who handle deployment.</span></span> <span data-ttu-id="0227e-175">文件扩展名为 xbap （适用于 XAML 浏览器应用程序（Xbap））和应用程序。</span><span class="sxs-lookup"><span data-stu-id="0227e-175">The file extension is .xbap (for XAML browser applications (XBAPs)) and .application for installed applications.</span></span> <span data-ttu-id="0227e-176">.xbap는 `HostInBrowser` 프로젝트 속성에 의해 지정되며 그 결과 매니페스트는 애플리케이션이 브라우저에 호스트되는 것으로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-176">The former is dictated by the `HostInBrowser` project property and as a result the manifest identifies the application as browser-hosted.</span></span>

<span data-ttu-id="0227e-177">애플리케이션 매니페스트(.exe.manifest 파일)는 애플리케이션 어셈블리 및 종속 라이브러리를 설명하고 애플리케이션에 필요한 사용 권한을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-177">The application manifest (an .exe.manifest file) describes the application assemblies and dependent libraries and lists permissions required by the application.</span></span> <span data-ttu-id="0227e-178">이 파일은 애플리케이션 개발자가 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-178">This file is intended to be authored by the application developer.</span></span> <span data-ttu-id="0227e-179">为了启动 ClickOnce 应用程序，用户将打开该应用程序的部署清单文件。</span><span class="sxs-lookup"><span data-stu-id="0227e-179">In order to launch a ClickOnce application, a user opens the application's deployment manifest file.</span></span>

<span data-ttu-id="0227e-180">这些清单文件始终为 Xbap 创建。</span><span class="sxs-lookup"><span data-stu-id="0227e-180">These manifest files are always created for XBAPs.</span></span> <span data-ttu-id="0227e-181">설치된 애플리케이션의 경우 프로젝트 파일에서 `GenerateManifests` 속성 값이 `true`로 지정되지 않는 한 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-181">For installed applications, they are not created unless the `GenerateManifests` property is specified in the project file with value `true`.</span></span>

<span data-ttu-id="0227e-182">Xbap 在分配给典型 Internet 区域应用程序的权限之上或更高的其他两个权限： <xref:System.Security.Permissions.WebBrowserPermission> 和 <xref:System.Security.Permissions.MediaPermission>。</span><span class="sxs-lookup"><span data-stu-id="0227e-182">XBAPs get two additional permissions over and above those permissions assigned to typical Internet zone applications: <xref:System.Security.Permissions.WebBrowserPermission> and <xref:System.Security.Permissions.MediaPermission>.</span></span> <span data-ttu-id="0227e-183">WPF 生成系统会在应用程序清单中声明这些权限。</span><span class="sxs-lookup"><span data-stu-id="0227e-183">The WPF build system declares those permissions in the application manifest.</span></span>

<a name="Incremental_Build_Support"></a>

## <a name="incremental-build-support"></a><span data-ttu-id="0227e-184">증분 빌드 지원</span><span class="sxs-lookup"><span data-stu-id="0227e-184">Incremental Build Support</span></span>

<span data-ttu-id="0227e-185">WPF 生成系统为增量生成提供支持。</span><span class="sxs-lookup"><span data-stu-id="0227e-185">The WPF build system provides support for incremental builds.</span></span> <span data-ttu-id="0227e-186">태그 또는 코드에 대한 변경 사항을 지능적으로 검색하고 변경 사항의 영향을 받는 아티팩트만 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-186">It is fairly intelligent about detecting changes made to markup or code, and it compiles only those artifacts affected by the change.</span></span> <span data-ttu-id="0227e-187">증분 빌드 메커니즘은 다음 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-187">The incremental build mechanism uses the following files:</span></span>

- <span data-ttu-id="0227e-188">현재 컴파일러 상태를 유지 관리하는 $(*AssemblyName*)_MarkupCompiler.Cache 파일</span><span class="sxs-lookup"><span data-stu-id="0227e-188">An $(*AssemblyName*)_MarkupCompiler.Cache file to maintain current compiler state.</span></span>

- <span data-ttu-id="0227e-189">로컬로 정의된 형식에 대한 참조가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 캐시하는 $(*AssemblyName*) _MarkupCompiler.lref 파일</span><span class="sxs-lookup"><span data-stu-id="0227e-189">An $(*AssemblyName*)_MarkupCompiler.lref file to cache the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files with references to locally defined types.</span></span>

<span data-ttu-id="0227e-190">다음은 증분 빌드를 제어하는 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-190">The following is a set of rules governing incremental build:</span></span>

- <span data-ttu-id="0227e-191">파일은 빌드 시스템이 변경을 검색하는 가장 작은 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-191">The file is the smallest unit at which the build system detects change.</span></span> <span data-ttu-id="0227e-192">따라서 코드 파일의 경우 빌드 시스템에서 형식이 변경되었는지 또는 코드가 추가되었는지 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-192">So, for a code file, the build system cannot tell if a type was changed or if code was added.</span></span> <span data-ttu-id="0227e-193">이는 프로젝트 파일도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-193">The same holds for project files.</span></span>

- <span data-ttu-id="0227e-194">증분 빌드 메커니즘은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 클래스를 정의하거나 다른 클래스를 사용한다는 것을 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-194">The incremental build mechanism must be cognizant that a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page either defines a class or uses other classes.</span></span>

- <span data-ttu-id="0227e-195">`Reference` 항목이 변경된 경우 모든 페이지를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-195">If `Reference` entries change, then recompile all pages.</span></span>

- <span data-ttu-id="0227e-196">코드 파일이 변경되면 로컬로 정의된 형식 참조가 있는 모든 페이지를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-196">If a code file changes, recompile all pages with locally defined type references.</span></span>

- <span data-ttu-id="0227e-197">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일이 변경된 경우:</span><span class="sxs-lookup"><span data-stu-id="0227e-197">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file changes:</span></span>

  - <span data-ttu-id="0227e-198">프로젝트에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]이 `Page`로 선언된 경우: [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 로컬로 정의된 형식 참조가 없는 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 로컬 참조와 함께 다시 컴파일합니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 로컬 참조가 있는 경우 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 로컬 참조와 함께 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-198">If [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is declared as `Page` in the project: if the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] does not have locally defined type references, recompile that [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] plus all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages with local references; if the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has local references, recompile all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages with local references.</span></span>

  - <span data-ttu-id="0227e-199">如果 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 在项目中声明为 `ApplicationDefinition`：重新编译所有 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页（原因：每个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 都引用了可能已更改的 <xref:System.Windows.Application> 类型）。</span><span class="sxs-lookup"><span data-stu-id="0227e-199">If [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is declared as `ApplicationDefinition` in the project: recompile all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages (reason: each [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has reference to an <xref:System.Windows.Application> type that may have changed).</span></span>

- <span data-ttu-id="0227e-200">프로젝트 파일에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 대신 애플리케이션 정의로 코드 파일을 선언한 경우:</span><span class="sxs-lookup"><span data-stu-id="0227e-200">If the project file declares a code file as application definition instead of a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file:</span></span>

  - <span data-ttu-id="0227e-201">프로젝트 파일의 `ApplicationClassName` 값이 변경되었는지(새로운 애플리케이션 형식이 있는지) 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-201">Check if the `ApplicationClassName` value in the project file has changed (is there a new application type?).</span></span> <span data-ttu-id="0227e-202">변경된 경우 전체 애플리케이션을 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-202">If so, recompile the entire application.</span></span>

  - <span data-ttu-id="0227e-203">변경되지 않은 경우 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 로컬 참조와 함께 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-203">Otherwise, recompile all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages with local references.</span></span>

- <span data-ttu-id="0227e-204">프로젝트 파일이 변경된 경우: 앞에서 설명한 규칙을 모두 적용하고 다시 컴파일해야 할 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-204">If a project file changes: apply all preceding rules and see what needs to be recompiled.</span></span> <span data-ttu-id="0227e-205">`AssemblyName`, `IntermediateOutputPath`, `RootNamespace` 및 `HostInBrowser` 속성이 변경되면 전체 다시 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-205">Changes to the following properties trigger a complete recompile: `AssemblyName`, `IntermediateOutputPath`, `RootNamespace`, and `HostInBrowser`.</span></span>

<span data-ttu-id="0227e-206">다시 컴파일 작업은 다음과 같은 시나리오로 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-206">The following recompile scenarios are possible:</span></span>

- <span data-ttu-id="0227e-207">전체 애플리케이션이 다시 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-207">The entire application is recompiled.</span></span>

- <span data-ttu-id="0227e-208">로컬로 정의된 형식 참조가 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일만 다시 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0227e-208">Only those [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that have locally defined type references are recompiled.</span></span>

- <span data-ttu-id="0227e-209">모든 항목이 다시 컴파일되지 않습니다(프로젝트의 모든 항목이 변경되지 않음).</span><span class="sxs-lookup"><span data-stu-id="0227e-209">Nothing is recompiled (if nothing in the project has changed).</span></span>

## <a name="see-also"></a><span data-ttu-id="0227e-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0227e-210">See also</span></span>

- [<span data-ttu-id="0227e-211">WPF 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="0227e-211">Deploying a WPF Application</span></span>](deploying-a-wpf-application-wpf.md)
- [<span data-ttu-id="0227e-212">WPF MSBuild 참조</span><span class="sxs-lookup"><span data-stu-id="0227e-212">WPF MSBuild Reference</span></span>](/visualstudio/msbuild/wpf-msbuild-reference)
- [<span data-ttu-id="0227e-213">WPF의 Pack URI</span><span class="sxs-lookup"><span data-stu-id="0227e-213">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
- [<span data-ttu-id="0227e-214">WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="0227e-214">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
