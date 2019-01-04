---
title: 启用 tab 自动补全
description: 本文介绍如何针对适用于 PowerShell、Bash 和 zsh 的 .NET Core CLI 启用 tab 自动补全。
author: thraka
ms.author: adegeo
ms.date: 12/17/2018
ms.openlocfilehash: 10b2e13aad9821295efc5c36d1cad04f1a95477c
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "53784387"
---
# <a name="how-to-enable-tab-completion-for-the-net-core-cli"></a><span data-ttu-id="e67e9-103">如何为 .NET Core CLI 启用 TAB 自动补全</span><span class="sxs-lookup"><span data-stu-id="e67e9-103">How to enable TAB completion for the .NET Core CLI</span></span>

<span data-ttu-id="e67e9-104">从.NET Core 2.0 SDK 开始，NET Core CLI 支持 tab 自动补全。</span><span class="sxs-lookup"><span data-stu-id="e67e9-104">Starting with .NET Core 2.0 SDK, the .NET Core CLI supports tab completion.</span></span> <span data-ttu-id="e67e9-105">本文介绍如何为三个 shell、PowerShell、Bash 和 zsh 配置 tab 自动补全。</span><span class="sxs-lookup"><span data-stu-id="e67e9-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="e67e9-106">其他 shell 可能支持自动补全功能。</span><span class="sxs-lookup"><span data-stu-id="e67e9-106">Other shells may have support for auto completion.</span></span> <span data-ttu-id="e67e9-107">请参阅有关如何配置自动补全功能的文档，这些步骤应与本文中介绍的步骤类似。</span><span class="sxs-lookup"><span data-stu-id="e67e9-107">Refer to their documentation on how to configure auto completion, the steps should be similar to the steps described in this article.</span></span>

[!INCLUDE [topic-appliesto-net-core-2plus](~/includes/topic-appliesto-net-core-2plus.md)]

<span data-ttu-id="e67e9-108">设置完成后，通过在 shell 中键入 `dotnet ` 命令，然后单击 TAB 键来触发 .NET Core CLI 的 tab 自动补全。</span><span class="sxs-lookup"><span data-stu-id="e67e9-108">Once setup, tab completion for the .NET Core CLI is triggered by typing a `dotnet ` command in the shell, and then hitting the TAB key.</span></span> <span data-ttu-id="e67e9-109">当前命令行将发送到 `dotnet complete` 命令，结果将由 shell 处理。</span><span class="sxs-lookup"><span data-stu-id="e67e9-109">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="e67e9-110">可以通过直接向 `dotnet complete` 命令发送内容来测试结果而无需启用 tab 自动补全。</span><span class="sxs-lookup"><span data-stu-id="e67e9-110">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="e67e9-111">例如:</span><span class="sxs-lookup"><span data-stu-id="e67e9-111">For example:</span></span>

```
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="e67e9-112">如果该命令不起作用，请确保已安装 .NET Core 2.0 SDK 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e67e9-112">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="e67e9-113">如果已安装，但该命令仍不起作用，请确保 `dotnet` 命令解析为 .NET Core 2.0 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="e67e9-113">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 and above.</span></span> <span data-ttu-id="e67e9-114">使用 `dotnet --version` 命令查看当前路径解析为的 `dotnet` 的版本。</span><span class="sxs-lookup"><span data-stu-id="e67e9-114">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="e67e9-115">有关详细信息，请参阅[选择要使用的 .NET Core 版本](../versions/selection.md)页面。</span><span class="sxs-lookup"><span data-stu-id="e67e9-115">For more information, see [Select the .NET Core version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="e67e9-116">示例</span><span class="sxs-lookup"><span data-stu-id="e67e9-116">Examples</span></span>

<span data-ttu-id="e67e9-117">下面是 tab 自动补全提供的一些示例：</span><span class="sxs-lookup"><span data-stu-id="e67e9-117">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="e67e9-118">输入</span><span class="sxs-lookup"><span data-stu-id="e67e9-118">Input</span></span>                                | <span data-ttu-id="e67e9-119">将变为</span><span class="sxs-lookup"><span data-stu-id="e67e9-119">becomes</span></span>                                                                     | <span data-ttu-id="e67e9-120">因为</span><span class="sxs-lookup"><span data-stu-id="e67e9-120">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="e67e9-121">`add` 是第一项子命令，按字母排序。</span><span class="sxs-lookup"><span data-stu-id="e67e9-121">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="e67e9-122">Tab 自动补全匹配子字符串，`--help` 首先按字母顺序排列。</span><span class="sxs-lookup"><span data-stu-id="e67e9-122">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="e67e9-123">第二次按 Tab 将显示下一条建议。</span><span class="sxs-lookup"><span data-stu-id="e67e9-123">Pressing tab a second time brings up the next suggestion.</span></span>      
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="e67e9-124">结果按字母顺序返回。</span><span class="sxs-lookup"><span data-stu-id="e67e9-124">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="e67e9-125">Tab 自动补全是可识别的项目文件。</span><span class="sxs-lookup"><span data-stu-id="e67e9-125">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="e67e9-126">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e67e9-126">PowerShell</span></span>

<span data-ttu-id="e67e9-127">要将 tab 自动补全添加到适用于 .NET Core CLI 的 PowerShell，请创建或编辑存储在变量 `$PROFILE` 中的配置文件。</span><span class="sxs-lookup"><span data-stu-id="e67e9-127">To add tab completion to **PowerShell** for the .NET Core CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="e67e9-128">有关详细信息，请参阅[如何创建配置文件](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile)和[配置文件和执行策略](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy)。</span><span class="sxs-lookup"><span data-stu-id="e67e9-128">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy).</span></span> 

<span data-ttu-id="e67e9-129">将以下代码添加到配置文件中：</span><span class="sxs-lookup"><span data-stu-id="e67e9-129">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI 
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="e67e9-130">Bash</span><span class="sxs-lookup"><span data-stu-id="e67e9-130">Bash</span></span>

<span data-ttu-id="e67e9-131">要将 tab 自动补全添加到适用于 .NET Core CLI 的 bash shell，请将以下代码添加到 `.bashrc` 文件：</span><span class="sxs-lookup"><span data-stu-id="e67e9-131">To add tab completion to your **bash** shell for the .NET Core CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}")"

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="e67e9-132">Zsh</span><span class="sxs-lookup"><span data-stu-id="e67e9-132">Zsh</span></span>

<span data-ttu-id="e67e9-133">要将 tab 自动补全添加到适用于 .NET Core CLI 的 zsh shell，请将以下代码添加到 `.zshrc` 文件：</span><span class="sxs-lookup"><span data-stu-id="e67e9-133">To add tab completion to your **zsh** shell for the .NET Core CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete() 
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
