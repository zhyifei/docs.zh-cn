---
title: 如何：对应用程序进行本地化
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: 1190fb739e7c1873532e96b50399ac0deb6bb51c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48782034"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="2bb1f-102">如何：对应用程序进行本地化</span><span class="sxs-lookup"><span data-stu-id="2bb1f-102">How to: Localize an Application</span></span>
<span data-ttu-id="2bb1f-103">本教程介绍如何通过使用 LocBaml 工具创建本地化应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bb1f-104">LocBaml 工具不是可直接用于生产的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="2bb1f-105">它表示为一个示例，该示例使用某些本地化 API 并演示编写一个本地化工具的方法。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
<a name="Introduction"></a>   
## <a name="overview"></a><span data-ttu-id="2bb1f-106">概述</span><span class="sxs-lookup"><span data-stu-id="2bb1f-106">Overview</span></span>  
 <span data-ttu-id="2bb1f-107">本讨论提供逐步实现本地化应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-107">This discussion gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="2bb1f-108">首先，你要准备应用程序，以便可以提取将被翻译的文本。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-108">First, you will prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="2bb1f-109">相关文本翻译后，你要将翻译的文本合并到原始应用程序的新副本中。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-109">After the text is translated, you will merge the translated text into a new copy of the original application.</span></span>  
  
<a name="Requirements"></a>   
## <a name="requirements"></a><span data-ttu-id="2bb1f-110">要求</span><span class="sxs-lookup"><span data-stu-id="2bb1f-110">Requirements</span></span>  
 <span data-ttu-id="2bb1f-111">在此讨论过程中，你将使用 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]，这是一个从命令行运行的编译器。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-111">Over the course of this discussion, you will use [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)], which is a compiler that runs from the command line.</span></span>  
  
 <span data-ttu-id="2bb1f-112">此外，还会指导你使用项目文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-112">Also, you will be instructed to use a project file.</span></span> <span data-ttu-id="2bb1f-113">有关说明如何使用[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]和项目文件，请参阅[生成并部署](../../../../docs/framework/wpf/app-development/building-and-deploying-wpf-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-113">For instructions on how to use [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] and project files, see [Build and Deploy](../../../../docs/framework/wpf/app-development/building-and-deploying-wpf-applications.md).</span></span>  
  
 <span data-ttu-id="2bb1f-114">在此讨论中的所有示例都使用 zh-CN（中文-中国）作为区域设置。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-114">All the examples in this discussion use en-US (English-US) as the culture.</span></span> <span data-ttu-id="2bb1f-115">这使你能够而无需安装另一种语言就能完成这些示例的步骤。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-115">This enables you to work through the steps of the examples without installing a different language.</span></span>  
  
<a name="create_sample_app"></a>   
## <a name="create-a-sample-application"></a><span data-ttu-id="2bb1f-116">创建一个简单的应用程序</span><span class="sxs-lookup"><span data-stu-id="2bb1f-116">Create a Sample Application</span></span>  
 <span data-ttu-id="2bb1f-117">在此步骤中，你将准备要用于本地化的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-117">In this step, you will prepare your application for localization.</span></span> <span data-ttu-id="2bb1f-118">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 示例提供了 HelloApp 示例，将用于本讨论中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-118">In the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="2bb1f-119">如果想要使用此示例中，下载[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件从[LocBaml 工具示例](https://go.microsoft.com/fwlink/?LinkID=160016)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-119">If you would like to use this sample, download the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
1.  <span data-ttu-id="2bb1f-120">将应用程序开发到想要开始进行本地化的位置。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-120">Develop your application to the point where you want to start localization.</span></span>  
  
2.  <span data-ttu-id="2bb1f-121">在项目文件中指定开发语言，以便 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] 生成主程序集和附属程序集（具有 .resources.dll 扩展的文件）以包含非特定语言资源。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-121">Specify the development language in the project file so that [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="2bb1f-122">HelloApp 示例中的项目文件是 HelloApp.csproj。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-122">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="2bb1f-123">在该文件中，你将找到标识如下的开发语言：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-123">In that file, you will find the development language identified as follows:</span></span>  
  
     `<UICulture>en-US</UICulture>`  
  
3.  <span data-ttu-id="2bb1f-124">将 Uid 添加到你的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-124">Add Uids to your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="2bb1f-125">Uid 用于跟踪对文件的更改并标识必须翻译的项。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-125">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="2bb1f-126">若要将 Uid 添加到你的文件，请运行**updateuid**上你的项目文件：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-126">To add Uids to your files, run **updateuid** on your project file:</span></span>  
  
     <span data-ttu-id="2bb1f-127">**msbuild t: updateuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="2bb1f-127">**msbuild -t:updateuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="2bb1f-128">若要验证没有缺少或重复的 Uid，请运行**checkuid**:</span><span class="sxs-lookup"><span data-stu-id="2bb1f-128">To verify that you have no missing or duplicate Uids, run **checkuid**:</span></span>  
  
     <span data-ttu-id="2bb1f-129">**msbuild t: checkuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="2bb1f-129">**msbuild -t:checkuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="2bb1f-130">运行之后**updateuid**，你的文件应包含 Uid。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-130">After running **updateuid**, your files should contain Uids.</span></span> <span data-ttu-id="2bb1f-131">例如，在 HelloApp 的 Pane1.xaml 文件中，你应能找到下列内容：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-131">For example, in the Pane1.xaml file of HelloApp, you should find the following:</span></span>  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>   
## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="2bb1f-132">创建非特定语言资源附属程序集</span><span class="sxs-lookup"><span data-stu-id="2bb1f-132">Create the Neutral Language Resources Satellite Assembly</span></span>  
 <span data-ttu-id="2bb1f-133">将应用程序配置为生成非特定语言资源附属程序集后，则可生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-133">After the application is configured to generate a neutral language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="2bb1f-134">这会生成主应用程序程序集，以及 LocBaml 本地化所需的非特定语言资源附属程序集。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-134">This generates the main application assembly, as well as the neutral language resources satellite assembly that is required by LocBaml for localization.</span></span> <span data-ttu-id="2bb1f-135">若要生成应用程序：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-135">To build the application:</span></span>  
  
1.  <span data-ttu-id="2bb1f-136">编译 HelloApp 以创建一个 [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)]：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-136">Compile HelloApp to create a [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)]:</span></span>  
  
     <span data-ttu-id="2bb1f-137">**msbuild helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="2bb1f-137">**msbuild helloapp.csproj**</span></span>  
  
2.  <span data-ttu-id="2bb1f-138">新创建的主应用程序程序集 HelloApp.exe 创建在下列文件夹中：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-138">The newly created main application assembly, HelloApp.exe, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\`  
  
3.  <span data-ttu-id="2bb1f-139">新创建的非特定语言资源附属程序集 HelloApp.resources.dll 创建在下列文件夹中：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-139">The newly created neutral language resources satellite assembly, HelloApp.resources.dll, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>   
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="2bb1f-140">生成 LocBaml 工具</span><span class="sxs-lookup"><span data-stu-id="2bb1f-140">Build the LocBaml Tool</span></span>  
  
1.  <span data-ttu-id="2bb1f-141">生成 LocBaml 所需的所有文件都位于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 示例中。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-141">All the files necessary to build LocBaml are located in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] samples.</span></span> <span data-ttu-id="2bb1f-142">下载 C# 文件从[LocBaml 工具示例](https://go.microsoft.com/fwlink/?LinkID=160016)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-142">Download the C# files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
2.  <span data-ttu-id="2bb1f-143">从命令行运行项目文件 (locbaml.csproj) 来生成该工具：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-143">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  
  
     <span data-ttu-id="2bb1f-144">**msbuild locbaml.csproj**</span><span class="sxs-lookup"><span data-stu-id="2bb1f-144">**msbuild locbaml.csproj**</span></span>  
  
3.  <span data-ttu-id="2bb1f-145">转到 Bin\Release 目录以查找新创建的可执行文件 (locbaml.exe)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-145">Go to the Bin\Release directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="2bb1f-146">示例：C:\LocBaml\Bin\Release\locbaml.exe。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span></span>  
  
4.  <span data-ttu-id="2bb1f-147">运行 LocBaml 时可指定下列选项：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-147">The options that you can specify when you run LocBaml are as follows:</span></span>  
  
    -   <span data-ttu-id="2bb1f-148">**分析**或 **-p:** 分析 Baml、 资源或[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]文件以生成.csv 或.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-148">**parse** or **-p:** Parses Baml, resources, or [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] files to generate a .csv or .txt file.</span></span>  
  
    -   <span data-ttu-id="2bb1f-149">**生成**或 **-g:** 通过使用翻译的文件生成本地化的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-149">**generate** or **-g:** Generates a localized binary file by using a translated file.</span></span>  
  
    -   <span data-ttu-id="2bb1f-150">**out**或 **-o** {*filedirectory*] **:** 输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-150">**out** or **-o** {*filedirectory*] **:** Output file name.</span></span>  
  
    -   <span data-ttu-id="2bb1f-151">**区域性**或 **-cul** {*区域性*] **:** 输出程序集的区域设置。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-151">**culture** or **-cul** {*culture*] **:** Locale of output assemblies.</span></span>  
  
    -   <span data-ttu-id="2bb1f-152">**翻译**或 **-trans** {*translation.csv*] **:** 经过翻译或本地化的文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-152">**translation** or **-trans** {*translation.csv*] **:** Translated or localized file.</span></span>  
  
    -   <span data-ttu-id="2bb1f-153">**asmpath**或 **-asmpath:** {*filedirectory*] **:** 如果你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]代码包含自定义控件，必须提供**asmpath**对自定义控件程序集。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-153">**asmpath** or **-asmpath:** {*filedirectory*] **:** If your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code contains custom controls, you must supply the **asmpath** to the custom control assembly.</span></span>  
  
    -   <span data-ttu-id="2bb1f-154">**nologo：** 显示没有徽标或版权信息。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-154">**nologo:** Displays no logo or copyright information.</span></span>  
  
    -   <span data-ttu-id="2bb1f-155">**verbose：** 显示详细模式信息。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-155">**verbose:** Displays verbose mode information.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bb1f-156">如果要在运行该工具时需要的选项的列表，请键入**LocBaml.exe**然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-156">If you need a list of the options when you are running the tool, type     **LocBaml.exe** and press ENTER.</span></span>  
  
<a name="parse_dll"></a>   
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="2bb1f-157">使用 LocBaml 分析文件</span><span class="sxs-lookup"><span data-stu-id="2bb1f-157">Use LocBaml to Parse a File</span></span>  
 <span data-ttu-id="2bb1f-158">由于已创建 LocBaml 工具，就可使用它来分析 HelloApp.resources.dll，从而提取将进行本地化的文本内容。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-158">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1.  <span data-ttu-id="2bb1f-159">将 LocBaml.exe 复制到应用程序的 bin\debug 文件夹，这也是创建主应用程序程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-159">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2.  <span data-ttu-id="2bb1f-160">若要分析附属程序集文件并将输出存储为 .csv 文件，请使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-160">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
     <span data-ttu-id="2bb1f-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span><span class="sxs-lookup"><span data-stu-id="2bb1f-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bb1f-162">如果输入文件 HelloApp.resources.dll 不在 LocBaml.exe 所在的同一目录中，请移动其中一个文件以使两个文件都位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-162">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3.  <span data-ttu-id="2bb1f-163">当运行 LocBaml 来分析文件时，输出包含由逗号（.csv 文件）或制表符（.txt 文件）分隔的七个字段。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-163">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="2bb1f-164">下面显示了 HelloApp.resources.dll 的已分析的 .csv 文件：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-164">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="2bb1f-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="2bb1f-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="2bb1f-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="2bb1f-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="2bb1f-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="2bb1f-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="2bb1f-168">这七个字段是：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-168">The seven fields are:</span></span>  
  
   1.  <span data-ttu-id="2bb1f-169">**BAML 名称**。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-169">**BAML Name**.</span></span> <span data-ttu-id="2bb1f-170">与源语言附属程序集相关的 BAML 资源的名称。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-170">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   2.  <span data-ttu-id="2bb1f-171">**资源键**。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-171">**Resource Key**.</span></span> <span data-ttu-id="2bb1f-172">本地化的资源标识符。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-172">The localized resource identifier.</span></span>  
  
   3.  <span data-ttu-id="2bb1f-173">**Category**。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-173">**Category**.</span></span> <span data-ttu-id="2bb1f-174">值类型。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-174">The value type.</span></span> <span data-ttu-id="2bb1f-175">请参阅[本地化特性和注释](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-175">See [Localization Attributes and Comments](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).</span></span>  
  
   4.  <span data-ttu-id="2bb1f-176">**Readability**。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-176">**Readability**.</span></span> <span data-ttu-id="2bb1f-177">值是否可以由本地化人员读取。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-177">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="2bb1f-178">请参阅[本地化特性和注释](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-178">See [Localization Attributes and Comments](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).</span></span>  
  
   5.  <span data-ttu-id="2bb1f-179">**Modifiability**。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-179">**Modifiability**.</span></span> <span data-ttu-id="2bb1f-180">值是否可以由本地化人员修改。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-180">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="2bb1f-181">请参阅[本地化特性和注释](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-181">See [Localization Attributes and Comments](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).</span></span>  
  
   6.  <span data-ttu-id="2bb1f-182">**注释**。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-182">**Comments**.</span></span> <span data-ttu-id="2bb1f-183">值的附加说明，用于确定值被本地化的方式。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-183">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="2bb1f-184">请参阅[本地化特性和注释](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-184">See [Localization Attributes and Comments](../../../../docs/framework/wpf/advanced/localization-attributes-and-comments.md).</span></span>  
  
   7.  <span data-ttu-id="2bb1f-185">**值**。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-185">**Value**.</span></span> <span data-ttu-id="2bb1f-186">要翻译为所需区域性设置的文本值。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-186">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="2bb1f-187">下表显示了这些字段映射到 .csv 文件的分隔值的方式：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-187">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="2bb1f-188">BAML 名称</span><span class="sxs-lookup"><span data-stu-id="2bb1f-188">BAML name</span></span>|<span data-ttu-id="2bb1f-189">资源键</span><span class="sxs-lookup"><span data-stu-id="2bb1f-189">Resource key</span></span>|<span data-ttu-id="2bb1f-190">类别</span><span class="sxs-lookup"><span data-stu-id="2bb1f-190">Category</span></span>|<span data-ttu-id="2bb1f-191">可读性</span><span class="sxs-lookup"><span data-stu-id="2bb1f-191">Readability</span></span>|<span data-ttu-id="2bb1f-192">可修改性</span><span class="sxs-lookup"><span data-stu-id="2bb1f-192">Modifiability</span></span>|<span data-ttu-id="2bb1f-193">注释</span><span class="sxs-lookup"><span data-stu-id="2bb1f-193">Comments</span></span>|<span data-ttu-id="2bb1f-194">值</span><span class="sxs-lookup"><span data-stu-id="2bb1f-194">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="2bb1f-195">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="2bb1f-195">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="2bb1f-196">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="2bb1f-196">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="2bb1f-197">忽略</span><span class="sxs-lookup"><span data-stu-id="2bb1f-197">Ignore</span></span>|<span data-ttu-id="2bb1f-198">FALSE</span><span class="sxs-lookup"><span data-stu-id="2bb1f-198">FALSE</span></span>|<span data-ttu-id="2bb1f-199">FALSE</span><span class="sxs-lookup"><span data-stu-id="2bb1f-199">FALSE</span></span>||<span data-ttu-id="2bb1f-200">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="2bb1f-200">#Text1;#Text2</span></span>|
   |<span data-ttu-id="2bb1f-201">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="2bb1f-201">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="2bb1f-202">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="2bb1f-202">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="2bb1f-203">无</span><span class="sxs-lookup"><span data-stu-id="2bb1f-203">None</span></span>|<span data-ttu-id="2bb1f-204">TRUE</span><span class="sxs-lookup"><span data-stu-id="2bb1f-204">TRUE</span></span>|<span data-ttu-id="2bb1f-205">TRUE</span><span class="sxs-lookup"><span data-stu-id="2bb1f-205">TRUE</span></span>||<span data-ttu-id="2bb1f-206">Hello World</span><span class="sxs-lookup"><span data-stu-id="2bb1f-206">Hello World</span></span>|
   |<span data-ttu-id="2bb1f-207">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="2bb1f-207">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="2bb1f-208">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="2bb1f-208">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="2bb1f-209">无</span><span class="sxs-lookup"><span data-stu-id="2bb1f-209">None</span></span>|<span data-ttu-id="2bb1f-210">TRUE</span><span class="sxs-lookup"><span data-stu-id="2bb1f-210">TRUE</span></span>|<span data-ttu-id="2bb1f-211">TRUE</span><span class="sxs-lookup"><span data-stu-id="2bb1f-211">TRUE</span></span>||<span data-ttu-id="2bb1f-212">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="2bb1f-212">Goodbye World</span></span>|
  
   <span data-ttu-id="2bb1f-213">请注意，所有值**注释**字段不包含任何值; 如果字段没有值，则为空。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-213">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="2bb1f-214">此外请注意第一行中的项既不可读也不可修改，并且拥有"Ignore"作为其**类别**值，这些都指示该值不可本地化。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-214">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4.  <span data-ttu-id="2bb1f-215">为了便于发现已分析的文件，特别是在大型文件中可本地化的项目可以进行排序或筛选的项**类别**，**可读性**，和**可修改性**.</span><span class="sxs-lookup"><span data-stu-id="2bb1f-215">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="2bb1f-216">例如，你可以筛选出不可读且不可修改的值。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-216">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
<a name="translate_loc_content"></a>   
## <a name="translate-the-localizable-content"></a><span data-ttu-id="2bb1f-217">翻译可本地化的内容</span><span class="sxs-lookup"><span data-stu-id="2bb1f-217">Translate the Localizable Content</span></span>  
 <span data-ttu-id="2bb1f-218">使用任何你可用的工具翻译提取的内容。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-218">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="2bb1f-219">执行此操作的一个好办法是将这些资源写入 .csv 文件，并在 [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] 中查看它们，对最后一列（值）作出翻译更改。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-219">A good way to do this is to write the resources to a .csv file and view them in [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)], making translation changes to the last column (value).</span></span>  
  
<a name="merge_translations"></a>   
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="2bb1f-220">使用 LocBaml 生成新的 .resources.dll 文件</span><span class="sxs-lookup"><span data-stu-id="2bb1f-220">Use LocBaml to Generate a New .resources.dll File</span></span>  
 <span data-ttu-id="2bb1f-221">通过使用 LocBaml 分析 HelloApp.resources.dll 而标识的内容已被翻译，且必须合并回原始应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-221">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="2bb1f-222">使用**生成**或 **-g**生成一个新的选项.resources.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-222">Use the **generate** or **-g** option to generate a new .resources.dll file.</span></span>  
  
1.  <span data-ttu-id="2bb1f-223">使用下列语法来生成新的 HelloApp.resources.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-223">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="2bb1f-224">将区域性标记为 zh-CN (/cul:zh-CN)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-224">Mark the culture as en-US (/cul:en-US).</span></span>  
  
     <span data-ttu-id="2bb1f-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span><span class="sxs-lookup"><span data-stu-id="2bb1f-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bb1f-226">如果输入文件 Hello.csv 与可执行文件 LocBaml.exe 不在的同一目录中，请移动其中一个文件以使两个文件都位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-226">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2.  <span data-ttu-id="2bb1f-227">使用新创建的 HelloApp.resources.dll 文件替换 C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll 目录中的旧 HelloApp.resources.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-227">Replace the old HelloApp.resources.dll file in the C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll directory with your newly created HelloApp.resources.dll file.</span></span>  
  
3.  <span data-ttu-id="2bb1f-228">应在你的应用程序中将“Hello World”和“Goodbye World”翻译过来。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-228">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4.  <span data-ttu-id="2bb1f-229">若要翻译到不同的区域性设置，请使用目标语言的区域设置。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-229">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="2bb1f-230">下列示例演示了如何翻译为加拿大法语：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-230">The following example shows how to translate to French-Canadian:</span></span>  
  
     <span data-ttu-id="2bb1f-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span><span class="sxs-lookup"><span data-stu-id="2bb1f-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span></span>  
  
5.  <span data-ttu-id="2bb1f-232">在主应用程序程序集所在的程序集，创建一个新的特定于区域性的文件夹，以容纳新的附属程序集。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-232">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="2bb1f-233">对于加拿大法语，该文件夹将为 fr-CA。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-233">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6.  <span data-ttu-id="2bb1f-234">将生成的附属程序集复制到新建文件夹。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-234">Copy the generated satellite assembly to the new folder.</span></span>  
  
7.  <span data-ttu-id="2bb1f-235">若要测试新的附属程序集，你需要更改应用程序将在其下运行的区域性设置。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-235">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="2bb1f-236">可以通过两种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-236">You can do this in one of two ways:</span></span>  
  
    -   <span data-ttu-id="2bb1f-237">更改操作系统的区域设置 (**启动** &#124; **控制面板** &#124; **区域和语言选项**)。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-237">Change your operating system's regional settings (**Start** &#124; **Control Panel** &#124; **Regional and Language Options**).</span></span>  
  
    -   <span data-ttu-id="2bb1f-238">在你的应用程序中，将下列代码添加到 App.xaml.cs 中：</span><span class="sxs-lookup"><span data-stu-id="2bb1f-238">In your application, add the following code to App.xaml.cs:</span></span>  
  
   [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
   [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
   [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>   
## <a name="some-tips-for-using-locbaml"></a><span data-ttu-id="2bb1f-239">使用 LocBaml 的一些提示</span><span class="sxs-lookup"><span data-stu-id="2bb1f-239">Some Tips for Using LocBaml</span></span>  
  
-   <span data-ttu-id="2bb1f-240">所有定义自定义控件的依赖程序集必须复制到 LocBaml 的本地目录，或安装到 GAC。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-240">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="2bb1f-241">这是必要的，因为本地化 API 在读取 [!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)] 时必须具有对依赖程序集的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-241">This is necessary because the localization API must have access to the dependent assemblies when it reads the [!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)].</span></span>  
  
-   <span data-ttu-id="2bb1f-242">如果主程序集已签名，则生成的资源 DLL 也必须签名以进行加载。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-242">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
-   <span data-ttu-id="2bb1f-243">本地化的资源 DLL 的版本需与主程序集进行同步。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-243">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>  
  
<a name="Whats_Next"></a>   
## <a name="whats-next"></a><span data-ttu-id="2bb1f-244">下一步</span><span class="sxs-lookup"><span data-stu-id="2bb1f-244">What's Next</span></span>  
 <span data-ttu-id="2bb1f-245">现在，你应该对如何使用 LocBaml 工具有了一个基本的了解。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-245">You should now have a basic understanding of how to use the LocBaml tool.</span></span>  <span data-ttu-id="2bb1f-246">你应该能够制作包含 Uid 的文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-246">You should be able to make a file that contains Uids.</span></span> <span data-ttu-id="2bb1f-247">通过使用 LocBaml 工具，你应该能够分析文件以提取可本地化的内容，并且在内容翻译后，你应该能够生成一个合并已翻译内容的 resources.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-247">By using the LocBaml tool, you should be able to parse a file to extract the localizable content, and after the content is translated, you should be able to generate a .resources.dll file that merges the translated content.</span></span> <span data-ttu-id="2bb1f-248">本主题不包括每个可能的细节，但现在你已经掌握了使用 LocBaml 对应用程序进行本地化的必要知识。</span><span class="sxs-lookup"><span data-stu-id="2bb1f-248">This topic does not include every possible detail, but you now have the knowledge necessary to use LocBaml for localizing your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb1f-249">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bb1f-249">See Also</span></span>  
 [<span data-ttu-id="2bb1f-250">WPF 全球化</span><span class="sxs-lookup"><span data-stu-id="2bb1f-250">Globalization for WPF</span></span>](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)  
 [<span data-ttu-id="2bb1f-251">使用自动布局概述</span><span class="sxs-lookup"><span data-stu-id="2bb1f-251">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)
