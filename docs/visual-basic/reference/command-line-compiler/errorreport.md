---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: c8e193a8cb4d4dbc7515c32139bad9dce8b48ed7
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005618"
---
# <a name="-errorreport"></a><span data-ttu-id="ccea9-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="ccea9-102">-errorreport</span></span>

<span data-ttu-id="ccea9-103">指定 Visual Basic 编译器如何报告内部编译器错误。</span><span class="sxs-lookup"><span data-stu-id="ccea9-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="ccea9-104">语法</span><span class="sxs-lookup"><span data-stu-id="ccea9-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="ccea9-105">备注</span><span class="sxs-lookup"><span data-stu-id="ccea9-105">Remarks</span></span>

<span data-ttu-id="ccea9-106">使用此选项可以方便地向 Microsoft 报告 Visual Basic 内部编译器错误（ICE）到 Visual Basic 团队。</span><span class="sxs-lookup"><span data-stu-id="ccea9-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="ccea9-107">默认情况下，编译器不向 Microsoft 发送任何信息。</span><span class="sxs-lookup"><span data-stu-id="ccea9-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="ccea9-108">但是，如果遇到内部编译器错误，则可以使用此选项向 Microsoft 报告错误。</span><span class="sxs-lookup"><span data-stu-id="ccea9-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="ccea9-109">该信息将帮助 Microsoft 工程师找出原因，并帮助改进 Visual Basic 的下一版本。</span><span class="sxs-lookup"><span data-stu-id="ccea9-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="ccea9-110">用户发送报表的能力取决于计算机和用户策略的权限。</span><span class="sxs-lookup"><span data-stu-id="ccea9-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="ccea9-111">下表总结了 `-errorreport` 选项的影响。</span><span class="sxs-lookup"><span data-stu-id="ccea9-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="ccea9-112">选项</span><span class="sxs-lookup"><span data-stu-id="ccea9-112">Option</span></span>|<span data-ttu-id="ccea9-113">行为</span><span class="sxs-lookup"><span data-stu-id="ccea9-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="ccea9-114">如果发生内部编译器错误，则会出现一个对话框，以便您可以查看编译器收集的确切数据。</span><span class="sxs-lookup"><span data-stu-id="ccea9-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="ccea9-115">您可以确定错误报告中是否存在任何敏感信息，并决定是否将其发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="ccea9-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="ccea9-116">如果你决定发送它，并且计算机和用户策略设置允许它，则编译器会将数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="ccea9-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="ccea9-117">将错误报告排入队列。</span><span class="sxs-lookup"><span data-stu-id="ccea9-117">Queues the error report.</span></span> <span data-ttu-id="ccea9-118">当你以管理员权限登录时，你可以报告自上次登录后发生的任何失败（系统将不会提示你每三天发送一次失败的报告）。</span><span class="sxs-lookup"><span data-stu-id="ccea9-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="ccea9-119">这是未指定 `-errorreport` 选项时的默认行为。</span><span class="sxs-lookup"><span data-stu-id="ccea9-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="ccea9-120">如果发生内部编译器错误，并且计算机和用户策略设置允许，则编译器会将数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="ccea9-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="ccea9-121">如果[Windows 错误报告](/windows/desktop/wer/windows-error-reporting)系统设置启用了报告，则选项 `-errorreport:send` 会尝试自动向 Microsoft 发送错误信息。</span><span class="sxs-lookup"><span data-stu-id="ccea9-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="ccea9-122">如果发生内部编译器错误，则不会将其收集或发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="ccea9-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="ccea9-123">编译器将在出现错误时发送包括堆栈的数据，这通常包括一些源代码。</span><span class="sxs-lookup"><span data-stu-id="ccea9-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="ccea9-124">如果 `-errorreport` 与[-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项一起使用，则将发送整个源文件。</span><span class="sxs-lookup"><span data-stu-id="ccea9-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="ccea9-125">此选项最适合用于[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，因为它允许 Microsoft 工程师更轻松地重现错误。</span><span class="sxs-lookup"><span data-stu-id="ccea9-125">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="ccea9-126">在 Visual Studio 开发环境中，不能使用 `-errorreport` 选项;仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="ccea9-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="ccea9-127">示例</span><span class="sxs-lookup"><span data-stu-id="ccea9-127">Example</span></span>

<span data-ttu-id="ccea9-128">下面的代码尝试编译 `T2.vb`，如果编译器遇到内部编译器错误，则会提示你将错误报告发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="ccea9-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="ccea9-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="ccea9-129">See also</span></span>

- [<span data-ttu-id="ccea9-130">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="ccea9-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ccea9-131">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="ccea9-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="ccea9-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="ccea9-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
