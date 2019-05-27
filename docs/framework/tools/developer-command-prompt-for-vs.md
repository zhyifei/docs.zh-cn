---
title: Visual Studio 开发人员命令提示
ms.date: 08/14/2018
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
ms.openlocfilehash: 79cfc607e20d921c7ae942cb9755eee4264336eb
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877042"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="d5e76-102">Visual Studio 开发人员命令提示</span><span class="sxs-lookup"><span data-stu-id="d5e76-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="d5e76-103">Visual Studio 的开发人员命令提示符使你可以更轻松地使用 .NET Framework 工具。</span><span class="sxs-lookup"><span data-stu-id="d5e76-103">The Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="d5e76-104">它是一个自动设置特定环境变量的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="d5e76-104">It is a command prompt that automatically sets specific environment variables.</span></span>

> [!div class="button"]
> [<span data-ttu-id="d5e76-105">下载 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d5e76-105">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="d5e76-106">在计算机中搜索命令提示符</span><span class="sxs-lookup"><span data-stu-id="d5e76-106">Search for the command prompt on your machine</span></span>

<span data-ttu-id="d5e76-107">你可能会有多个命令提示符，具体取决于你安装的 Visual Studio 及其他任何 SDK 的版本。</span><span class="sxs-lookup"><span data-stu-id="d5e76-107">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="d5e76-108">例如，Visual Studio 的 64 位版本同时提供 32 位和 64 位命令提示。</span><span class="sxs-lookup"><span data-stu-id="d5e76-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="d5e76-109">（大多数工具的 32 位和 64 位版本都相同；但少数工具针对具体的 32 位和 64 位环境做了一些改变。）如果以下步骤不起作用，可以尝试[在计算机中手动查找文件](#manually-locate-the-files-on-your-machine)或[从 Visual Studio 内部运行命令提示符](#run-the-command-prompt-from-inside-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="d5e76-109">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [Run the command prompt from inside Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="d5e76-110">在 Windows 10 中</span><span class="sxs-lookup"><span data-stu-id="d5e76-110">In Windows 10</span></span>

1. <span data-ttu-id="d5e76-111">在任务栏的搜索框中，开始键入工具的名称，例如 `dev` 或 `developer command prompt`。</span><span class="sxs-lookup"><span data-stu-id="d5e76-111">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="d5e76-112">然后显示一个列表，其中包含与搜索模式匹配的已安装应用。</span><span class="sxs-lookup"><span data-stu-id="d5e76-112">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="d5e76-113">如果要查找不同的命令提示，请尝试输入不同的搜索词，例如 `prompt`。</span><span class="sxs-lookup"><span data-stu-id="d5e76-113">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="d5e76-114">选择“Visual Studio 开发人员命令提示”（或者你想使用的命令提示）。</span><span class="sxs-lookup"><span data-stu-id="d5e76-114">Choose the **Developer Command Prompt for Visual Studio** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="d5e76-115">在 Windows 8.1 中</span><span class="sxs-lookup"><span data-stu-id="d5e76-115">In Windows 8.1</span></span>

1. <span data-ttu-id="d5e76-116">按 Windows 徽标键![键盘上的 Windows 徽标键](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)，转到“开始”屏幕。</span><span class="sxs-lookup"><span data-stu-id="d5e76-116">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="d5e76-117">例如，在键盘上。</span><span class="sxs-lookup"><span data-stu-id="d5e76-117">on your keyboard for example.</span></span>

2. <span data-ttu-id="d5e76-118">在“开始”屏幕上，按 Ctrl+Tab 打开“应用程序”列表，然后输入 `V`。</span><span class="sxs-lookup"><span data-stu-id="d5e76-118">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then enter `V`.</span></span> <span data-ttu-id="d5e76-119">然后显示一个列表，其中包含所有已安装的 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="d5e76-119">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="d5e76-120">选择“开发人员命令提示”（或者你想使用的命令提示）。</span><span class="sxs-lookup"><span data-stu-id="d5e76-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="d5e76-121">在 Windows 8 中</span><span class="sxs-lookup"><span data-stu-id="d5e76-121">In Windows 8</span></span>

1. <span data-ttu-id="d5e76-122">按 Windows 徽标键![键盘上的 Windows 徽标键](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)，转到“开始”屏幕。</span><span class="sxs-lookup"><span data-stu-id="d5e76-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="d5e76-123">例如，在键盘上。</span><span class="sxs-lookup"><span data-stu-id="d5e76-123">on your keyboard for example.</span></span>

2. <span data-ttu-id="d5e76-124">在“开始”屏幕上，按 Windows 徽标键![键盘上的 Windows 徽标键](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)。</span><span class="sxs-lookup"><span data-stu-id="d5e76-124">On the **Start** screen, press the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="d5e76-125">`+ Z`。</span><span class="sxs-lookup"><span data-stu-id="d5e76-125">`+ Z`.</span></span>

3. <span data-ttu-id="d5e76-126">选择屏幕底部的“应用视图”图标，然后输入 `V`。</span><span class="sxs-lookup"><span data-stu-id="d5e76-126">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="d5e76-127">然后显示一个列表，其中包含所有已安装的 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="d5e76-127">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="d5e76-128">选择“开发人员命令提示”（或者你想使用的命令提示）。</span><span class="sxs-lookup"><span data-stu-id="d5e76-128">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="d5e76-129">在 Windows 7 中</span><span class="sxs-lookup"><span data-stu-id="d5e76-129">In Windows 7</span></span>

1. <span data-ttu-id="d5e76-130">选择“开始”，展开“所有程序”，然后展开“Microsoft Visual Studio”。</span><span class="sxs-lookup"><span data-stu-id="d5e76-130">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="d5e76-131">根据已安装的 Visual Studio 版本，选择“Visual Studio Tools”、“Visual Studio 命令提示”或你想使用的命令提示。</span><span class="sxs-lookup"><span data-stu-id="d5e76-131">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="d5e76-132">如果安装了其他 SDK，例如 [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 或[之前的版本](https://developer.microsoft.com/windows/downloads/sdk-archive)，则可能看到有关 ARM、x86 或 x64 体系结构的其他命令提示符。</span><span class="sxs-lookup"><span data-stu-id="d5e76-132">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="d5e76-133">查看单个工具的文档，以确定应使用哪个版本的命令提示。</span><span class="sxs-lookup"><span data-stu-id="d5e76-133">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="d5e76-134">在计算机中手动查找文件</span><span class="sxs-lookup"><span data-stu-id="d5e76-134">Manually locate the files on your machine</span></span>

<span data-ttu-id="d5e76-135">已安装的命令提示的快捷方式通常放在 Visual Studio 的“开始菜单”文件夹中，例如 C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools。</span><span class="sxs-lookup"><span data-stu-id="d5e76-135">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="d5e76-136">但是如果出于某种原因，搜索命令提示未产生预期的效果，你可以尝试在计算机中手动查找快捷方式。</span><span class="sxs-lookup"><span data-stu-id="d5e76-136">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="d5e76-137">请尝试搜索命令提示文件的名称，例如 VsDevCmd.bat，或者转到“工具”文件夹，例如 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools（该路径根据你的 Visual Studio 版本和安装位置而变化）。</span><span class="sxs-lookup"><span data-stu-id="d5e76-137">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="d5e76-138">从 Visual Studio 内部运行命令提示符</span><span class="sxs-lookup"><span data-stu-id="d5e76-138">Run the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="d5e76-139">为便于访问，你可以将 Visual Studio 开发人员命令提示或其他任何命令提示符添加到 Visual Studio 中的“工具”菜单中。</span><span class="sxs-lookup"><span data-stu-id="d5e76-139">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="d5e76-140">要使该工具可用，请将其添加到外部工具列表中。</span><span class="sxs-lookup"><span data-stu-id="d5e76-140">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="d5e76-141">步骤如下：</span><span class="sxs-lookup"><span data-stu-id="d5e76-141">Here are the steps:</span></span>

1. <span data-ttu-id="d5e76-142">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d5e76-142">Open Visual Studio.</span></span>

2. <span data-ttu-id="d5e76-143">选择“工具”菜单，然后选择“外部工具”。</span><span class="sxs-lookup"><span data-stu-id="d5e76-143">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="d5e76-144">在“外部工具”对话框中，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="d5e76-144">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="d5e76-145">随即出现一个新项。</span><span class="sxs-lookup"><span data-stu-id="d5e76-145">A new entry appears.</span></span>

4. <span data-ttu-id="d5e76-146">为新菜单项输入“标题”，例如 `Command Prompt`。</span><span class="sxs-lookup"><span data-stu-id="d5e76-146">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="d5e76-147">在“命令”字段中，指定要启动的文件，例如 `%comspec%` 或 `C:\Windows\System32\cmd.exe`。</span><span class="sxs-lookup"><span data-stu-id="d5e76-147">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="d5e76-148">在“参数”字段中，指定可在其中找到要使用的特定命令提示的位置，例如 `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"`（此命令启动随 Visual Studio 2017 Enterprise 一起安装的开发人员命令提示）。</span><span class="sxs-lookup"><span data-stu-id="d5e76-148">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="d5e76-149">根据 Visual Studio 版本和安装位置更改此值。</span><span class="sxs-lookup"><span data-stu-id="d5e76-149">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="d5e76-150">为“初始目录”字段选择一个值，例如“项目目录”。</span><span class="sxs-lookup"><span data-stu-id="d5e76-150">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="d5e76-151">选择“确定”  按钮。</span><span class="sxs-lookup"><span data-stu-id="d5e76-151">Choose the **OK** button.</span></span>

   <span data-ttu-id="d5e76-152">系统添加了新菜单项，并且你可以从“工具”菜单访问命令提示符。</span><span class="sxs-lookup"><span data-stu-id="d5e76-152">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

   ![Visual Studio 中的命令提示符菜单项](media/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="d5e76-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5e76-154">See also</span></span>

- [<span data-ttu-id="d5e76-155">工具</span><span class="sxs-lookup"><span data-stu-id="d5e76-155">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="d5e76-156">管理外部工具</span><span class="sxs-lookup"><span data-stu-id="d5e76-156">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
