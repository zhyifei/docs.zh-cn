---
title: Visual Studio 开发人员命令提示
ms.date: 06/18/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8e64facffd4face929b28d660ffd5210f127c3bd
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315220"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="2ae3d-102">Visual Studio 开发人员命令提示</span><span class="sxs-lookup"><span data-stu-id="2ae3d-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="2ae3d-103">Visual Studio 开发人员命令提示会自动设置环境变量，这些变量使你能够轻松使用 .NET Framework 工具。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="2ae3d-104">安装完整版或社区版 Visual Studio 时会安装开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="2ae3d-105">安装 Express 版 Visual Studio 时不会安装。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-105">It isn't installed with the Express versions of Visual Studio.</span></span>

> [!div class="button"]
[<span data-ttu-id="2ae3d-106">下载 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2ae3d-106">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="2ae3d-107">在计算机中搜索命令提示</span><span class="sxs-lookup"><span data-stu-id="2ae3d-107">Searching for the Command Prompt on your machine</span></span>

<span data-ttu-id="2ae3d-108">可能会看到多个命令提示，具体取决于你安装的 Visual Studio 及其他任何 SDK 的版本。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-108">You may see many command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="2ae3d-109">例如，Visual Studio 的 64 位版本同时提供 32 位和 64 位命令提示。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-109">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="2ae3d-110">（大多数工具的 32 位和 64 位版本都相同；但少数工具针对具体的 32 位和 64 位环境做了一些改变。）如果以下步骤不起作用，可以尝试[在计算机中手动查找文件](#manually-locating-the-files-on-your-machine)或[从 Visual Studio 内部运行命令提示](#running-command-prompt-from-inside-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-110">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locating the files on your machine](#manually-locating-the-files-on-your-machine) or [Running command prompt from inside Visual Studio](#running-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="2ae3d-111">在 Windows 10 中</span><span class="sxs-lookup"><span data-stu-id="2ae3d-111">In Windows 10</span></span>

1. <span data-ttu-id="2ae3d-112">在任务栏的搜索框中，开始键入工具的名称，例如 `dev` 或 `developer command prompt`。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-112">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="2ae3d-113">然后显示一个列表，其中包含与搜索模式匹配的已安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-113">This brings a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="2ae3d-114">如果要查找不同的命令提示，请尝试输入不同的搜索词，例如 `prompt`。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="2ae3d-115">选择“开发人员命令提示”（或者你想使用的命令提示）。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="2ae3d-116">在 Windows 8.1 中</span><span class="sxs-lookup"><span data-stu-id="2ae3d-116">In Windows 8.1</span></span>

1. <span data-ttu-id="2ae3d-117">通过按键盘上的 Windows 徽标键 ![Windows 徽标](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")（举例说明），转到“开始”屏幕。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="2ae3d-118">在“开始”屏幕上，按 `CTRL + TAB` 打开“应用”列表，然后输入 `V`。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="2ae3d-119">然后显示一个列表，其中包含所有已安装的 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-119">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="2ae3d-120">选择“开发人员命令提示”（或者你想使用的命令提示）。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="2ae3d-121">在 Windows 8 中</span><span class="sxs-lookup"><span data-stu-id="2ae3d-121">In Windows 8</span></span>

1. <span data-ttu-id="2ae3d-122">通过按键盘上的 Windows 徽标键 ![Windows 徽标](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")（举例说明），转到“开始”屏幕。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="2ae3d-123">在“开始”屏幕上，按 Windows 徽标键 ![Windows 徽标](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-123">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="2ae3d-124">选择屏幕底部的“应用视图”图标，然后输入 `V`。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="2ae3d-125">然后显示一个列表，其中包含所有已安装的 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-125">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="2ae3d-126">选择“开发人员命令提示”（或者你想使用的命令提示）。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="2ae3d-127">在 Windows 7 中</span><span class="sxs-lookup"><span data-stu-id="2ae3d-127">In Windows 7</span></span>

1. <span data-ttu-id="2ae3d-128">选择“开始”，展开“所有程序”，然后展开“Microsoft Visual Studio”。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="2ae3d-129">根据已安装的 Visual Studio 版本，选择“Visual Studio Tools”、“Visual Studio 命令提示”或你想使用的命令提示。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-129">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="2ae3d-130">如果安装了其他 SDK，例如 [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 或[之前的版本](https://developer.microsoft.com/windows/downloads/sdk-archive)，则可能看到有关 ARM、x86 或 x64 体系结构的额外命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-130">If you have other SDKs installed such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="2ae3d-131">查看单个工具的文档，以确定应使用哪个版本的命令提示。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="2ae3d-132">在计算机中手动查找文件</span><span class="sxs-lookup"><span data-stu-id="2ae3d-132">Manually locating the files on your machine</span></span>

<span data-ttu-id="2ae3d-133">已安装的命令提示的快捷方式通常放在 Visual Studio 的“开始菜单”文件夹中，例如 C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-133">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="2ae3d-134">但是如果出于某种原因，搜索命令提示未产生预期的效果，你可以尝试在计算机中手动查找快捷方式。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-134">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="2ae3d-135">请尝试搜索命令提示文件的名称，例如 VsDevCmd.bat，或者转到“工具”文件夹，例如 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools（该路径根据你的 Visual Studio 版本和安装位置而变化）。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-135">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="2ae3d-136">从 Visual Studio 内部运行命令提示</span><span class="sxs-lookup"><span data-stu-id="2ae3d-136">Running command prompt from inside Visual Studio</span></span>

<span data-ttu-id="2ae3d-137">为便于访问，你可以将 Visual Studio 开发人员命令提示或其他任何命令提示添加到 Visual Studio 的“工具”菜单中，方法是将其添加到外部工具列表中。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="2ae3d-138">下面说明了如何实现此操作：</span><span class="sxs-lookup"><span data-stu-id="2ae3d-138">This is how you can accomplish that:</span></span>

1. <span data-ttu-id="2ae3d-139">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-139">Open Visual Studio.</span></span>

2. <span data-ttu-id="2ae3d-140">选择“工具”菜单并选择“外部工具”。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-140">Select the **Tools** menu and choose **External Tools**.</span></span>

3. <span data-ttu-id="2ae3d-141">在“外部工具”对话框中，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="2ae3d-142">随即出现一个新项。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-142">A new entry appears.</span></span>

4. <span data-ttu-id="2ae3d-143">为新菜单项输入“标题”，例如 `Command Prompt`。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="2ae3d-144">在“命令”字段中，指定要启动的文件，例如 `%comspec%` 或 `C:\Windows\System32\cmd.exe`。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="2ae3d-145">在“参数”字段中，指定可在其中找到要使用的特定命令提示的位置，例如 `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"`（此命令启动随 Visual Studio 2017 Enterprise 一起安装的开发人员命令提示）。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="2ae3d-146">根据 Visual Studio 版本和安装位置更改此值。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="2ae3d-147">为“初始目录”字段选择一个值，例如“项目目录”。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-147">Choose a value for the **Initial directory** field such as **Project Directory**.</span></span>

8. <span data-ttu-id="2ae3d-148">选择“确定”  按钮。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-148">Choose the **OK** button.</span></span>

<span data-ttu-id="2ae3d-149">完成这些步骤后，系统会添加新的菜单项，你可以从“工具”菜单访问命令提示。</span><span class="sxs-lookup"><span data-stu-id="2ae3d-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ae3d-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ae3d-150">See also</span></span>

 [<span data-ttu-id="2ae3d-151">工具</span><span class="sxs-lookup"><span data-stu-id="2ae3d-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="2ae3d-152">管理外部工具</span><span class="sxs-lookup"><span data-stu-id="2ae3d-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)  
