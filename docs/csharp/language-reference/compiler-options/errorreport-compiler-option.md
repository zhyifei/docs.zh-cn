---
title: -errorreport（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
ms.openlocfilehash: 52b58aac5e82d4228dfda9c4d77c1d1c5de3e0cd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253884"
---
# <a name="-errorreport-c-compiler-options"></a><span data-ttu-id="e93f8-102">-errorreport（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="e93f8-102">-errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="e93f8-103">此选项提供向 Microsoft 报告 C# 内部编译错误的简便方法。</span><span class="sxs-lookup"><span data-stu-id="e93f8-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="e93f8-104">在 Windows Vista 和 Windows Server 2008 上，为 Visual Studio 制定的错误报告设置不会替代通过 Windows 错误报告 (WER) 制定的设置。</span><span class="sxs-lookup"><span data-stu-id="e93f8-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="e93f8-105">WER 设置始终优先于 Visual Studio 错误报告设置。</span><span class="sxs-lookup"><span data-stu-id="e93f8-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>

## <a name="syntax"></a><span data-ttu-id="e93f8-106">语法</span><span class="sxs-lookup"><span data-stu-id="e93f8-106">Syntax</span></span>

```console
-errorreport:{ none | prompt | queue | send }
```

## <a name="arguments"></a><span data-ttu-id="e93f8-107">参数</span><span class="sxs-lookup"><span data-stu-id="e93f8-107">Arguments</span></span>
 <span data-ttu-id="e93f8-108">**none**</span><span class="sxs-lookup"><span data-stu-id="e93f8-108">**none**</span></span>  
 <span data-ttu-id="e93f8-109">不收集有关内部编译器错误的报告，或不向 Microsoft 发送报告。</span><span class="sxs-lookup"><span data-stu-id="e93f8-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>

 <span data-ttu-id="e93f8-110">**prompt** 当你收到内部编译器错误时，提示你发送报告。</span><span class="sxs-lookup"><span data-stu-id="e93f8-110">**prompt** Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="e93f8-111">**提示**是在开发环境中编译应用程序时的默认值。</span><span class="sxs-lookup"><span data-stu-id="e93f8-111">**prompt** is the default when you compile an application in the development environment.</span></span>

 <span data-ttu-id="e93f8-112">**queue** 将错误报告排入队列。</span><span class="sxs-lookup"><span data-stu-id="e93f8-112">**queue** Queues the error report.</span></span> <span data-ttu-id="e93f8-113">使用管理凭据登录时，可以报告自上次登录以来的任何故障。</span><span class="sxs-lookup"><span data-stu-id="e93f8-113">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="e93f8-114">系统最多每 3 天 1 次提醒你发送故障报告。</span><span class="sxs-lookup"><span data-stu-id="e93f8-114">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="e93f8-115">**排队**是在命令行编译应用程序时的默认值。</span><span class="sxs-lookup"><span data-stu-id="e93f8-115">**queue** is the default when you compile an application at the command line.</span></span>

 <span data-ttu-id="e93f8-116">**send** 自动向 Microsoft 发送内部编译器错误报告。</span><span class="sxs-lookup"><span data-stu-id="e93f8-116">**send** Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="e93f8-117">若要启用此选项，必须首先同意 Microsoft 数据收集策略。</span><span class="sxs-lookup"><span data-stu-id="e93f8-117">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="e93f8-118">首次在计算机上指定 -errorreport:send 时，编译器消息将引导你访问包含 Microsoft 数据收集策略的网站  。</span><span class="sxs-lookup"><span data-stu-id="e93f8-118">The first time that you specify **-errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>

## <a name="remarks"></a><span data-ttu-id="e93f8-119">备注</span><span class="sxs-lookup"><span data-stu-id="e93f8-119">Remarks</span></span>
 <span data-ttu-id="e93f8-120">当编译器无法处理源代码文件时，会导致内部编译器错误 (ICE)。</span><span class="sxs-lookup"><span data-stu-id="e93f8-120">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="e93f8-121">出现 ICE 时，编译器不会生成可用于修复代码的输出文件或任何有用的诊断。</span><span class="sxs-lookup"><span data-stu-id="e93f8-121">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>

 <span data-ttu-id="e93f8-122">在早期版本中，收到 ICE 时，我们欢迎你与 Microsoft 产品支持服务联系以报告问题。</span><span class="sxs-lookup"><span data-stu-id="e93f8-122">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="e93f8-123">通过使用 -errorreport，可向 Visual C# 团队提供 ICE 信息  。</span><span class="sxs-lookup"><span data-stu-id="e93f8-123">By using **-errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="e93f8-124">你的错误报告可以帮助改进未来的编译器版本。</span><span class="sxs-lookup"><span data-stu-id="e93f8-124">Your error reports can help improve future compiler releases.</span></span>

 <span data-ttu-id="e93f8-125">用户能否发送报告取决于计算机和用户策略权限。</span><span class="sxs-lookup"><span data-stu-id="e93f8-125">A user's ability to send reports depends on computer and user policy permissions.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e93f8-126">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="e93f8-126">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="e93f8-127">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="e93f8-127">Open the project's **Properties** page.</span></span> <span data-ttu-id="e93f8-128">有关详细信息，请参阅 [“项目设计器”->“生成”页 (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)。</span><span class="sxs-lookup"><span data-stu-id="e93f8-128">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>

2. <span data-ttu-id="e93f8-129">单击“生成”  属性页。</span><span class="sxs-lookup"><span data-stu-id="e93f8-129">Click the **Build** property page.</span></span>

3. <span data-ttu-id="e93f8-130">单击 **“高级”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e93f8-130">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="e93f8-131">修改“内部编译器错误报告”  属性。</span><span class="sxs-lookup"><span data-stu-id="e93f8-131">Modify the **Internal Compiler Error Reporting** property.</span></span>

 <span data-ttu-id="e93f8-132">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>。</span><span class="sxs-lookup"><span data-stu-id="e93f8-132">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="e93f8-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e93f8-133">See also</span></span>

- [<span data-ttu-id="e93f8-134">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="e93f8-134">C# Compiler Options</span></span>](./index.md)
