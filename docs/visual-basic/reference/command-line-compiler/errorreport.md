---
title: -errorreport
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59dc833299161eac7b119e654c94534f202b1cb7
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-errorreport"></a><span data-ttu-id="84b17-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="84b17-102">-errorreport</span></span>
<span data-ttu-id="84b17-103">指定 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器应报告内部编译器错误的方式。</span><span class="sxs-lookup"><span data-stu-id="84b17-103">Specifies how the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b17-104">语法</span><span class="sxs-lookup"><span data-stu-id="84b17-104">Syntax</span></span>  
  
```  
-errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="84b17-105">备注</span><span class="sxs-lookup"><span data-stu-id="84b17-105">Remarks</span></span>  
 <span data-ttu-id="84b17-106">此选项可以方便地向报表[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]到内部编译器错误 (ICE) [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="84b17-106">This option provides a convenient way to report a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] internal compiler error (ICE) to the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] team at Microsoft.</span></span> <span data-ttu-id="84b17-107">默认情况下，编译器会向 Microsoft 发送任何信息。</span><span class="sxs-lookup"><span data-stu-id="84b17-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="84b17-108">但是，如果您遇到内部编译器错误，此选项允许你向 Microsoft 报告错误。</span><span class="sxs-lookup"><span data-stu-id="84b17-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="84b17-109">该信息将帮助 Microsoft 工程师确定原因以及可帮助改善的下一个版本[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="84b17-109">That information will help Microsoft engineers identify the cause and may help improve the next release of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="84b17-110">发送报表用户的能力取决于计算机和用户策略权限。</span><span class="sxs-lookup"><span data-stu-id="84b17-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="84b17-111">下表总结了的效果`-errorreport`选项。</span><span class="sxs-lookup"><span data-stu-id="84b17-111">The following table summarizes the effect of the `-errorreport` option.</span></span>  
  
|<span data-ttu-id="84b17-112">选项</span><span class="sxs-lookup"><span data-stu-id="84b17-112">Option</span></span>|<span data-ttu-id="84b17-113">行为</span><span class="sxs-lookup"><span data-stu-id="84b17-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="84b17-114">如果发生内部编译器错误，弹出对话框，以便你可以查看编译器收集的确切数据。</span><span class="sxs-lookup"><span data-stu-id="84b17-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="84b17-115">你可以判断是否有任何错误报告中的敏感信息和做出决策的是否将其发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="84b17-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="84b17-116">如果你决定发送它，并且计算机和用户策略设置允许它，编译器会将数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="84b17-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="84b17-117">将错误报告排入队列。</span><span class="sxs-lookup"><span data-stu-id="84b17-117">Queues the error report.</span></span> <span data-ttu-id="84b17-118">当使用管理员特权登录时，可以报告自上次登录以来的任何故障 （你不会提示发送故障报告一次以上每隔三天）。</span><span class="sxs-lookup"><span data-stu-id="84b17-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="84b17-119">这是默认行为时`-errorreport`未指定选项。</span><span class="sxs-lookup"><span data-stu-id="84b17-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="84b17-120">如果发生内部编译器错误，并且计算机和用户策略设置允许它，编译器会将数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="84b17-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="84b17-121">选项`-errorreport:send`尝试自动向 Microsoft 发送错误的信息。</span><span class="sxs-lookup"><span data-stu-id="84b17-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="84b17-122">此选项将依赖于注册表中。</span><span class="sxs-lookup"><span data-stu-id="84b17-122">This option depends on the registry.</span></span> <span data-ttu-id="84b17-123">有关在注册表中设置适当的值的详细信息，请参阅[如何自动错误报告在 Visual Studio 2008 命令行工具中打开](http://go.microsoft.com/fwlink/?LinkID=184695)。</span><span class="sxs-lookup"><span data-stu-id="84b17-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="84b17-124">如果发生内部编译器错误，它不会收集或发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="84b17-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="84b17-125">编译器将发送一个错误，它通常包含某些源代码时包括堆栈的数据。</span><span class="sxs-lookup"><span data-stu-id="84b17-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="84b17-126">如果`-errorreport`用于[-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，然后发送整个源文件。</span><span class="sxs-lookup"><span data-stu-id="84b17-126">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="84b17-127">此选项最适合用于[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，因为它可让 Microsoft 工程师能更轻松地再现错误。</span><span class="sxs-lookup"><span data-stu-id="84b17-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84b17-128">`-errorreport`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="84b17-128">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84b17-129">示例</span><span class="sxs-lookup"><span data-stu-id="84b17-129">Example</span></span>  
 <span data-ttu-id="84b17-130">下面的代码尝试编译`T2.vb`，如果编译器遇到内部编译器错误，它会提示你向 Microsoft 发送错误报告。</span><span class="sxs-lookup"><span data-stu-id="84b17-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc -errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="84b17-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84b17-131">See Also</span></span>  
 [<span data-ttu-id="84b17-132">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="84b17-132">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="84b17-133">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="84b17-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="84b17-134">-bugreport</span><span class="sxs-lookup"><span data-stu-id="84b17-134">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
