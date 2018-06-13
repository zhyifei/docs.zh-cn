---
title: Visual Studio 开发人员命令提示
ms.date: 03/30/2017
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
ms.openlocfilehash: d3ff897e37e3fa2f7202a54c05c8093ba05282c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402023"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="0476b-102">Visual Studio 开发人员命令提示</span><span class="sxs-lookup"><span data-stu-id="0476b-102">Developer Command Prompt for Visual Studio</span></span>
<span data-ttu-id="0476b-103">Visual Studio 开发人员命令提示会自动设置环境变量，这些变量使你能够轻松使用 .NET Framework 工具。</span><span class="sxs-lookup"><span data-stu-id="0476b-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="0476b-104">安装完整版或社区版 Visual Studio 时会安装开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="0476b-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="0476b-105">安装 Express 版 Visual Studio 时不会安装。</span><span class="sxs-lookup"><span data-stu-id="0476b-105">It is not installed with the Express versions of Visual Studio.</span></span>  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="0476b-106">在计算机中搜索命令提示</span><span class="sxs-lookup"><span data-stu-id="0476b-106">Searching for the Command Prompt on your machine</span></span>  
 <span data-ttu-id="0476b-107">你可能会看到多个命令提示，具体取决于你安装的 Visual Studio 及其他任何 SDK 的版本。</span><span class="sxs-lookup"><span data-stu-id="0476b-107">You may see multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="0476b-108">例如，Visual Studio 的 64 位版本同时提供 32 位和 64 位命令提示。</span><span class="sxs-lookup"><span data-stu-id="0476b-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="0476b-109">（大多数工具的 32 位和 64 位版本都相同；但少数工具针对具体的 32 位和 64 位环境做了一些改变。）如果以下步骤不起作用，可以尝试[在计算机中手动查找文件](#alternative)或[从 Visual Studio 内部运行命令提示](#visualstudio)。</span><span class="sxs-lookup"><span data-stu-id="0476b-109">(The 32-bit and 64-bit versions of most tools are identical; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the steps below don't work, you can try [Manually locating the files on your machine](#alternative) or [Running command prompt from inside Visual Studio](#visualstudio).</span></span>  
  
 <span data-ttu-id="0476b-110">**在 Windows 10 中**</span><span class="sxs-lookup"><span data-stu-id="0476b-110">**In Windows 10**</span></span>  
  
1.  <span data-ttu-id="0476b-111">通过按键盘上的 Windows 徽标键 ![Windows 徽标](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")（举例说明），打开“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="0476b-111">Open the **Start** menu, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="0476b-112">在“开始”菜单上，输入 `dev`。</span><span class="sxs-lookup"><span data-stu-id="0476b-112">On the **Start** menu, enter `dev`.</span></span> <span data-ttu-id="0476b-113">此时将显示一个列表，其中包含与搜索模式匹配的已安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="0476b-113">This will bring a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="0476b-114">如果要查找不同的命令提示，请尝试输入不同的搜索词，例如 `prompt`。</span><span class="sxs-lookup"><span data-stu-id="0476b-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>  
  
3.  <span data-ttu-id="0476b-115">选择“开发人员命令提示”（或者你想使用的命令提示）。</span><span class="sxs-lookup"><span data-stu-id="0476b-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="0476b-116">**在 Windows 8.1 中**</span><span class="sxs-lookup"><span data-stu-id="0476b-116">**In Windows 8.1**</span></span>  
  
1.  <span data-ttu-id="0476b-117">通过按键盘上的 Windows 徽标键 ![Windows 徽标](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")（举例说明），转到“开始”屏幕。</span><span class="sxs-lookup"><span data-stu-id="0476b-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="0476b-118">在“开始”屏幕上，按 `CTRL + TAB` 打开“应用”列表，然后输入 `V`。</span><span class="sxs-lookup"><span data-stu-id="0476b-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="0476b-119">此时将显示一个列表，其中包含所有已安装的 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="0476b-119">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
3.  <span data-ttu-id="0476b-120">选择“开发人员命令提示”（或者你想使用的命令提示）。</span><span class="sxs-lookup"><span data-stu-id="0476b-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="0476b-121">**在 Windows 8 中**</span><span class="sxs-lookup"><span data-stu-id="0476b-121">**In Windows 8**</span></span>  
  
1.  <span data-ttu-id="0476b-122">通过按键盘上的 Windows 徽标键 ![Windows 徽标](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")（举例说明），转到“开始”屏幕。</span><span class="sxs-lookup"><span data-stu-id="0476b-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="0476b-123">在“开始”屏幕上，按 Windows 徽标键 ![Windows 徽标](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`。</span><span class="sxs-lookup"><span data-stu-id="0476b-123">On the **Start** screen, press the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>  
  
3.  <span data-ttu-id="0476b-124">选择屏幕底部的“应用视图”图标，然后输入 `V`。</span><span class="sxs-lookup"><span data-stu-id="0476b-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="0476b-125">此时将显示一个列表，其中包含所有已安装的 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="0476b-125">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
4.  <span data-ttu-id="0476b-126">选择“开发人员命令提示”（或者你想使用的命令提示）。</span><span class="sxs-lookup"><span data-stu-id="0476b-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="0476b-127">**在 Windows 7 中**</span><span class="sxs-lookup"><span data-stu-id="0476b-127">**In Windows 7**</span></span>  
  
1.  <span data-ttu-id="0476b-128">选择“开始”，展开“所有程序”，然后展开“Microsoft Visual Studio”。</span><span class="sxs-lookup"><span data-stu-id="0476b-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="0476b-129">根据已安装的 Visual Studio 版本，选择“Visual Studio Tools”、“Visual Studio 命令提示”或你想使用的命令提示。</span><span class="sxs-lookup"><span data-stu-id="0476b-129">Depending on the version of Visual Studio you have installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>  
  
 <span data-ttu-id="0476b-130">如果安装了 [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) 或 [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk)，则可能会看到 ARM、x86 或 x64 体系结构的其他命令提示。</span><span class="sxs-lookup"><span data-stu-id="0476b-130">If you have the [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) or [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="0476b-131">查看单个工具的文档，以确定应使用哪个版本的命令提示。</span><span class="sxs-lookup"><span data-stu-id="0476b-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="0476b-132">在计算机中手动查找文件</span><span class="sxs-lookup"><span data-stu-id="0476b-132">Manually locating the files on your machine</span></span>  
  <span data-ttu-id="0476b-133">已安装的命令提示的快捷方式通常放在 Visual Studio 的“Start Menu”文件夹中，例如 C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools。</span><span class="sxs-lookup"><span data-stu-id="0476b-133">Usually, the shortcuts for the command prompts you have installed will be placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools.</span></span>    <span data-ttu-id="0476b-134">但是如果出于某种原因，搜索命令提示未产生预期的效果，你可以尝试在计算机中手动查找快捷方式，以便使用该快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0476b-134">But if for some reason, searching for the command prompt doesn't yield the expected results, you can try to manually locate the shortcut on your machine in order to use it.</span></span>   <span data-ttu-id="0476b-135">请尝试搜索命令提示文件的名称，例如 VsDevCmd.bat，或者转到 Tools 文件夹，例如 C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools（该路径将根据你的 Visual Studio 版本和安装位置而变化）。</span><span class="sxs-lookup"><span data-stu-id="0476b-135">Try searching for the name of the command prompt file such as VsDevCmd.bat or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools (path will change according to your Visual Studio version and installation location).</span></span>  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="0476b-136">从 Visual Studio 内部运行命令提示</span><span class="sxs-lookup"><span data-stu-id="0476b-136">Running command prompt from inside Visual Studio</span></span>  
 <span data-ttu-id="0476b-137">为便于访问，你可以将 Visual Studio 开发人员命令提示或其他任何命令提示添加到 Visual Studio 的“工具”菜单中，方法是将其添加到外部工具列表中。</span><span class="sxs-lookup"><span data-stu-id="0476b-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="0476b-138">下面说明了如何实现此操作：</span><span class="sxs-lookup"><span data-stu-id="0476b-138">This is how you can accomplish that:</span></span>  
  
1.  <span data-ttu-id="0476b-139">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="0476b-139">Open Visual Studio.</span></span>  
  
2.  <span data-ttu-id="0476b-140">选择“工具”菜单并选择“外部工具...”。</span><span class="sxs-lookup"><span data-stu-id="0476b-140">Select the **Tools** menu and choose **External Tools...**.</span></span>  
  
3.  <span data-ttu-id="0476b-141">在“外部工具”对话框中，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="0476b-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="0476b-142">随即出现一个新项</span><span class="sxs-lookup"><span data-stu-id="0476b-142">A new entry appears</span></span>  
  
4.  <span data-ttu-id="0476b-143">为新菜单项输入“标题”，例如 `Command Prompt`。</span><span class="sxs-lookup"><span data-stu-id="0476b-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>  
  
5.  <span data-ttu-id="0476b-144">在“命令”字段中，指定要启动的文件，例如 `%comspec%` 或 `C:\Windows\System32\cmd.exe`。</span><span class="sxs-lookup"><span data-stu-id="0476b-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe` .</span></span>  
  
6.  <span data-ttu-id="0476b-145">在“参数”字段中，指定可在其中找到要使用的特定命令提示的位置，例如 `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"`（这将启动随 [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)] 一起安装的开发人员命令提示）。</span><span class="sxs-lookup"><span data-stu-id="0476b-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (this will launch the Developer Command Prompt installed with [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]).</span></span> <span data-ttu-id="0476b-146">此值需根据 Visual Studio 版本和安装位置进行更改。</span><span class="sxs-lookup"><span data-stu-id="0476b-146">This value needs to be changed according to your Visual Studio version and installation location.</span></span>  
  
7.  <span data-ttu-id="0476b-147">为“初始目录”字段选择一个值，例如“项目目录”。</span><span class="sxs-lookup"><span data-stu-id="0476b-147">Choose a value for the **Initial directory** field such as **Project Directory** .</span></span>  
  
8.  <span data-ttu-id="0476b-148">选择“确定”  按钮。</span><span class="sxs-lookup"><span data-stu-id="0476b-148">Choose the **OK** button.</span></span>  
  
 <span data-ttu-id="0476b-149">完成这些步骤后，系统会添加新的菜单项，你可以从“工具”菜单访问命令提示。</span><span class="sxs-lookup"><span data-stu-id="0476b-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0476b-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="0476b-150">See Also</span></span>  
 [<span data-ttu-id="0476b-151">工具</span><span class="sxs-lookup"><span data-stu-id="0476b-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="0476b-152">管理外部工具</span><span class="sxs-lookup"><span data-stu-id="0476b-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
