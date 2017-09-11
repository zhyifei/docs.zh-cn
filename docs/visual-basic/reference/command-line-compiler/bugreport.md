---
title: "/bugreport |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b959ef7958cffbbb31f3907eaf8749ca93ac538d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="bugreport"></a><span data-ttu-id="94e26-102">/bugreport</span><span class="sxs-lookup"><span data-stu-id="94e26-102">/bugreport</span></span>
<span data-ttu-id="94e26-103">创建时归档 bug 报告，可以使用一个文件。</span><span class="sxs-lookup"><span data-stu-id="94e26-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e26-104">语法</span><span class="sxs-lookup"><span data-stu-id="94e26-104">Syntax</span></span>  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="94e26-105">参数</span><span class="sxs-lookup"><span data-stu-id="94e26-105">Arguments</span></span>  
  
|<span data-ttu-id="94e26-106">术语</span><span class="sxs-lookup"><span data-stu-id="94e26-106">Term</span></span>|<span data-ttu-id="94e26-107">定义</span><span class="sxs-lookup"><span data-stu-id="94e26-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="94e26-108">必需。</span><span class="sxs-lookup"><span data-stu-id="94e26-108">Required.</span></span> <span data-ttu-id="94e26-109">将包含错误报告文件的名称。</span><span class="sxs-lookup"><span data-stu-id="94e26-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="94e26-110">将文件名括在双引号 ("") 如果名称包含空格。</span><span class="sxs-lookup"><span data-stu-id="94e26-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94e26-111">备注</span><span class="sxs-lookup"><span data-stu-id="94e26-111">Remarks</span></span>  
 <span data-ttu-id="94e26-112">以下信息添加到`file`:</span><span class="sxs-lookup"><span data-stu-id="94e26-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="94e26-113">在编译中的所有源代码文件的副本。</span><span class="sxs-lookup"><span data-stu-id="94e26-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="94e26-114">编译器选项编译中使用的列表。</span><span class="sxs-lookup"><span data-stu-id="94e26-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="94e26-115">有关编译器、 公共语言运行时和操作系统版本信息。</span><span class="sxs-lookup"><span data-stu-id="94e26-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="94e26-116">编译器输出中，如果有的话。</span><span class="sxs-lookup"><span data-stu-id="94e26-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="94e26-117">此问题，它向您发出提示的说明。</span><span class="sxs-lookup"><span data-stu-id="94e26-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="94e26-118">应先修复您的想法问题的说明，提示你。</span><span class="sxs-lookup"><span data-stu-id="94e26-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="94e26-119">因为所有源代码文件的副本包含在`file`，可能需要重现尽可能短的程序中 （可疑的） 代码缺陷。</span><span class="sxs-lookup"><span data-stu-id="94e26-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="94e26-120">`/bugreport`选项将生成包含潜在的敏感信息的文件。</span><span class="sxs-lookup"><span data-stu-id="94e26-120">The `/bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="94e26-121">这包括当前时间，编译器版本[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]版本、 操作系统版本、 用户名称、 与其编译器是否运行，所有的源代码，以及二进制形式的所有被引用程序集的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="94e26-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="94e26-122">此选项可以通过指定的服务器端汇集的 Web.config 文件中的命令行选项[!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="94e26-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] application.</span></span> <span data-ttu-id="94e26-123">若要避免此情形，修改 Machine.config 文件，以便不允许用户在服务器上进行编译。</span><span class="sxs-lookup"><span data-stu-id="94e26-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="94e26-124">如果此选项用于`/errorreport:prompt`， `/errorreport:queue`，或`/errorreport:send`，并且您的应用程序遇到内部编译器错误中的信息`file`发送到 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="94e26-124">If this option is used with `/errorreport:prompt`, `/errorreport:queue`, or `/errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="94e26-125">该信息将帮助确定错误原因的 Microsoft 工程师以及可帮助改善的下一个版本[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="94e26-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="94e26-126">默认情况下，任何信息不发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="94e26-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="94e26-127">但是，当您编译应用程序使用`/errorreport:queue`，可以启用默认情况下，应用程序收集其错误报告。</span><span class="sxs-lookup"><span data-stu-id="94e26-127">However, when you compile an application by using `/errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="94e26-128">然后，在计算机的管理员登录，错误报告系统将显示一个弹出窗口，使管理员能够将转发给 Microsoft 任何错误报告自登录之后发生。</span><span class="sxs-lookup"><span data-stu-id="94e26-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94e26-129">`/bugreport`选项不是在 Visual Studio 开发环境中可用，可仅编译时从命令行。</span><span class="sxs-lookup"><span data-stu-id="94e26-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e26-130">示例</span><span class="sxs-lookup"><span data-stu-id="94e26-130">Example</span></span>  
 <span data-ttu-id="94e26-131">下面的示例将编译`T2.vb`并将错误报告的所有信息都放入该文件`Problem.txt`。</span><span class="sxs-lookup"><span data-stu-id="94e26-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="94e26-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94e26-132">See Also</span></span>  
 <span data-ttu-id="94e26-133">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="94e26-133">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="94e26-134"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="94e26-134"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="94e26-135"> [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span><span class="sxs-lookup"><span data-stu-id="94e26-135"> [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span></span>  
<span data-ttu-id="94e26-136"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="94e26-136"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="94e26-137"> [（ASP.NET 设置架构） securityPolicy 的 trustLevel 元素](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span><span class="sxs-lookup"><span data-stu-id="94e26-137"> [trustLevel Element for securityPolicy (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span></span>
