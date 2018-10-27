---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: 5471f0783eee5e2c14cf0f140094d5c292a73756
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50186771"
---
# <a name="-errorreport"></a><span data-ttu-id="39dbd-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="39dbd-102">-errorreport</span></span>

<span data-ttu-id="39dbd-103">指定 Visual Basic 编译器应报告内部编译器错误的方式。</span><span class="sxs-lookup"><span data-stu-id="39dbd-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="39dbd-104">语法</span><span class="sxs-lookup"><span data-stu-id="39dbd-104">Syntax</span></span>

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="39dbd-105">备注</span><span class="sxs-lookup"><span data-stu-id="39dbd-105">Remarks</span></span>

<span data-ttu-id="39dbd-106">此选项提供了 Visual Basic 团队在 Microsoft Visual Basic 内部编译器错误 (ICE) 报告的简便方法。</span><span class="sxs-lookup"><span data-stu-id="39dbd-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="39dbd-107">默认情况下，编译器会向 Microsoft 发送任何信息。</span><span class="sxs-lookup"><span data-stu-id="39dbd-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="39dbd-108">但是，如果执行操作时遇到内部编译器错误，此选项允许你向 Microsoft 报告错误。</span><span class="sxs-lookup"><span data-stu-id="39dbd-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="39dbd-109">该信息将帮助 Microsoft 工程师确定原因以及可帮助提高下一版本的 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="39dbd-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="39dbd-110">发送报表的用户的能力取决于计算机和用户策略权限。</span><span class="sxs-lookup"><span data-stu-id="39dbd-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="39dbd-111">下表总结了的效果`-errorreport`选项。</span><span class="sxs-lookup"><span data-stu-id="39dbd-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="39dbd-112">选项</span><span class="sxs-lookup"><span data-stu-id="39dbd-112">Option</span></span>|<span data-ttu-id="39dbd-113">行为</span><span class="sxs-lookup"><span data-stu-id="39dbd-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="39dbd-114">如果发生内部编译器错误，弹出对话框，以便您可以查看编译器收集的确切数据。</span><span class="sxs-lookup"><span data-stu-id="39dbd-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="39dbd-115">可以判断是否有错误报告中的任何敏感信息并决定将其发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="39dbd-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="39dbd-116">如果你决定发送它，并且计算机和用户策略设置允许它，编译器会将数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="39dbd-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="39dbd-117">将错误报告排入队列。</span><span class="sxs-lookup"><span data-stu-id="39dbd-117">Queues the error report.</span></span> <span data-ttu-id="39dbd-118">当使用管理员权限登录时，可以报告自上次登录以来的任何失败 （将不会提示您发送一次每隔三天的故障报告）。</span><span class="sxs-lookup"><span data-stu-id="39dbd-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="39dbd-119">这是默认行为时`-errorreport`未指定选项。</span><span class="sxs-lookup"><span data-stu-id="39dbd-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="39dbd-120">发生内部编译器错误，并将计算机和用户策略设置允许它，编译器会向 Microsoft 发送数据。</span><span class="sxs-lookup"><span data-stu-id="39dbd-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="39dbd-121">选项`-errorreport:send`尝试自动向 Microsoft 发送错误的信息，如果通过启用报告[Windows 错误报告](/windows/desktop/wer/windows-error-reporting)系统设置。</span><span class="sxs-lookup"><span data-stu-id="39dbd-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="39dbd-122">如果发生内部编译器错误，它不会收集或发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="39dbd-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="39dbd-123">编译器将发送包含一个错误，它通常包含某些源代码时堆栈的数据。</span><span class="sxs-lookup"><span data-stu-id="39dbd-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="39dbd-124">如果`-errorreport`用于[-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，则发送整个源文件。</span><span class="sxs-lookup"><span data-stu-id="39dbd-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="39dbd-125">此选项最适合用于[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，因为它可让 Microsoft 工程师更轻松地重现错误。</span><span class="sxs-lookup"><span data-stu-id="39dbd-125">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="39dbd-126">`-errorreport`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。</span><span class="sxs-lookup"><span data-stu-id="39dbd-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="39dbd-127">示例</span><span class="sxs-lookup"><span data-stu-id="39dbd-127">Example</span></span>

<span data-ttu-id="39dbd-128">下面的代码尝试编译`T2.vb`，如果编译器遇到内部编译器错误时，它会提示你向 Microsoft 发送错误报告。</span><span class="sxs-lookup"><span data-stu-id="39dbd-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="39dbd-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="39dbd-129">See also</span></span>

- [<span data-ttu-id="39dbd-130">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="39dbd-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="39dbd-131">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="39dbd-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="39dbd-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="39dbd-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
