---
title: Storeadm.exe（独立存储工具）
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 906d9d4dfd1c1082a4b49b7143f590967dcc7fd0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092261"
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="8a529-102">Storeadm.exe（独立存储工具）</span><span class="sxs-lookup"><span data-stu-id="8a529-102">Storeadm.exe (Isolated Storage Tool)</span></span>
<span data-ttu-id="8a529-103">独立存储工具列出或移除当前用户的所有现有存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-103">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="8a529-104">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="8a529-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="8a529-105">若要运行此工具，请使用 Visual Studio 开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="8a529-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="8a529-106">有关详细信息，请参阅[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="8a529-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="8a529-107">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="8a529-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a529-108">语法</span><span class="sxs-lookup"><span data-stu-id="8a529-108">Syntax</span></span>  
  
```  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a529-109">参数</span><span class="sxs-lookup"><span data-stu-id="8a529-109">Parameters</span></span>  
  
|<span data-ttu-id="8a529-110">选项</span><span class="sxs-lookup"><span data-stu-id="8a529-110">Option</span></span>|<span data-ttu-id="8a529-111">说明</span><span class="sxs-lookup"><span data-stu-id="8a529-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8a529-112">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="8a529-112">**/h**[**elp**]</span></span>|<span data-ttu-id="8a529-113">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="8a529-113">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="8a529-114">/list</span><span class="sxs-lookup"><span data-stu-id="8a529-114">**/list**</span></span>|<span data-ttu-id="8a529-115">显示当前用户的所有现有存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-115">Displays all existing stores for the current user.</span></span> <span data-ttu-id="8a529-116">这包括该用户执行的所有应用程序或程序集的存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-116">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="8a529-117">/machine</span><span class="sxs-lookup"><span data-stu-id="8a529-117">**/machine**</span></span>|<span data-ttu-id="8a529-118">选择计算机存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-118">Selects the machine store.</span></span> <span data-ttu-id="8a529-119">将此选项与 /list 或 /remove 选项一起使用可指定操作将应用于计算机存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-119">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="8a529-120">.NET Framework 2.0 的新增功能</span><span class="sxs-lookup"><span data-stu-id="8a529-120">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="8a529-121">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="8a529-121">**/quiet**</span></span>|<span data-ttu-id="8a529-122">指定安静模式；取消信息性输出以便只显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="8a529-122">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="8a529-123">/remove</span><span class="sxs-lookup"><span data-stu-id="8a529-123">**/remove**</span></span>|<span data-ttu-id="8a529-124">永久性移除当前用户的所有现有存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-124">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="8a529-125">/roaming</span><span class="sxs-lookup"><span data-stu-id="8a529-125">**/roaming**</span></span>|<span data-ttu-id="8a529-126">选择漫游存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-126">Selects the roaming store.</span></span> <span data-ttu-id="8a529-127">将此选项与 /list 或 /remove 选项一起使可指定操作将应用于漫游存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-127">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="8a529-128">**/?**</span><span class="sxs-lookup"><span data-stu-id="8a529-128">**/?**</span></span>|<span data-ttu-id="8a529-129">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="8a529-129">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a529-130">备注</span><span class="sxs-lookup"><span data-stu-id="8a529-130">Remarks</span></span>  
 <span data-ttu-id="8a529-131">如果从命令行运行 Storeadm.exe 但不指定任何选项，则将显示此工具的语法和选项。</span><span class="sxs-lookup"><span data-stu-id="8a529-131">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="8a529-132">/list 和 /remove 选项通常一次使用一个；但如果指定了两个或两个以上的选项，则它们将按照在命令行上出现的顺序执行。</span><span class="sxs-lookup"><span data-stu-id="8a529-132">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="8a529-133">应用程序可以选择保存到两个用户存储之一或保存到计算机存储：</span><span class="sxs-lookup"><span data-stu-id="8a529-133">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
-   <span data-ttu-id="8a529-134">本地存储位于保证不会漫游的位置（在 Windows 2000 及更高版本中），即使为用户启用了用户数据漫游也是如此。</span><span class="sxs-lookup"><span data-stu-id="8a529-134">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
-   <span data-ttu-id="8a529-135">漫游存储位于能够漫游的位置，但只有通过 Windows NT 管理为用户启用了漫游后才可做到这一点。</span><span class="sxs-lookup"><span data-stu-id="8a529-135">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
-   <span data-ttu-id="8a529-136">计算机存储对于计算机上的所有用户是公共的，并且它存储在该计算机上的公共目录下。</span><span class="sxs-lookup"><span data-stu-id="8a529-136">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8a529-137">计算机存储是 .NET Framework 2.0 版中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="8a529-137">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="8a529-138">实际上，是否为用户启用漫游并不会影响 Storeadm.exe 的管理。</span><span class="sxs-lookup"><span data-stu-id="8a529-138">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="8a529-139">在不使用任何选项的情况下运行此工具会向本地存储应用所有操作。</span><span class="sxs-lookup"><span data-stu-id="8a529-139">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="8a529-140">在使用 /roaming 选项的情况下运行此工具会将所有操作应用于可漫游的存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-140">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="8a529-141">在使用 /machine 选项的情况下运行此工具会将所有操作应用于计算机存储。</span><span class="sxs-lookup"><span data-stu-id="8a529-141">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a529-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a529-142">See also</span></span>

- [<span data-ttu-id="8a529-143">工具</span><span class="sxs-lookup"><span data-stu-id="8a529-143">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="8a529-144">独立存储</span><span class="sxs-lookup"><span data-stu-id="8a529-144">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
- [<span data-ttu-id="8a529-145">命令提示</span><span class="sxs-lookup"><span data-stu-id="8a529-145">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
