---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 75c3e5842447a8f0812d5a90d7157f7a6a496936
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962447"
---
# <a name="-bugreport"></a><span data-ttu-id="d210c-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="d210c-102">-bugreport</span></span>
<span data-ttu-id="d210c-103">创建一个文件, 该文件可在您提交 bug 报告时使用。</span><span class="sxs-lookup"><span data-stu-id="d210c-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d210c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d210c-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d210c-105">自变量</span><span class="sxs-lookup"><span data-stu-id="d210c-105">Arguments</span></span>  
  
|<span data-ttu-id="d210c-106">术语</span><span class="sxs-lookup"><span data-stu-id="d210c-106">Term</span></span>|<span data-ttu-id="d210c-107">定义</span><span class="sxs-lookup"><span data-stu-id="d210c-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="d210c-108">必需。</span><span class="sxs-lookup"><span data-stu-id="d210c-108">Required.</span></span> <span data-ttu-id="d210c-109">将包含 bug 报告的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d210c-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="d210c-110">如果名称包含空格, 请将文件名用引号 ("") 引起来。</span><span class="sxs-lookup"><span data-stu-id="d210c-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d210c-111">备注</span><span class="sxs-lookup"><span data-stu-id="d210c-111">Remarks</span></span>  
 <span data-ttu-id="d210c-112">以下信息已添加到`file`:</span><span class="sxs-lookup"><span data-stu-id="d210c-112">The following information is added to `file`:</span></span>  
  
- <span data-ttu-id="d210c-113">编译中所有源代码文件的副本。</span><span class="sxs-lookup"><span data-stu-id="d210c-113">A copy of all source-code files in the compilation.</span></span>  
  
- <span data-ttu-id="d210c-114">在编译中使用的编译器选项的列表。</span><span class="sxs-lookup"><span data-stu-id="d210c-114">A list of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="d210c-115">有关编译器、公共语言运行时和操作系统的版本信息。</span><span class="sxs-lookup"><span data-stu-id="d210c-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
- <span data-ttu-id="d210c-116">编译器输出（如有）。</span><span class="sxs-lookup"><span data-stu-id="d210c-116">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="d210c-117">提示你的问题的说明。</span><span class="sxs-lookup"><span data-stu-id="d210c-117">A description of the problem, for which you are prompted.</span></span>  
  
- <span data-ttu-id="d210c-118">有关你如何思考问题的说明, 请对此进行提示。</span><span class="sxs-lookup"><span data-stu-id="d210c-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="d210c-119">由于中`file`包含所有源代码文件的副本, 因此你可能需要在最短的程序中再现 (怀疑) 代码缺陷。</span><span class="sxs-lookup"><span data-stu-id="d210c-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d210c-120">选项`-bugreport`将生成一个包含潜在敏感信息的文件。</span><span class="sxs-lookup"><span data-stu-id="d210c-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="d210c-121">这包括当前时间、编译器版本、.NET Framework 版本、OS 版本、用户名、运行编译器时所用的命令行参数、所有源代码和任何被引用程序集的二进制格式。</span><span class="sxs-lookup"><span data-stu-id="d210c-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="d210c-122">通过在 web.config 文件中为 ASP.NET 应用程序的服务器端编译指定命令行选项, 可以访问此选项。</span><span class="sxs-lookup"><span data-stu-id="d210c-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="d210c-123">若要防止出现这种情况, 请修改 Machine.config 文件, 禁止用户在服务器上进行编译。</span><span class="sxs-lookup"><span data-stu-id="d210c-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="d210c-124">如果此选项`-errorreport:prompt`与、 `-errorreport:queue`或`-errorreport:send`一起使用, 并且你的应用程序遇到内部编译器错误, 则中`file`的信息将发送到 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="d210c-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="d210c-125">该信息将帮助 Microsoft 工程师找出错误的原因, 并帮助改进 Visual Basic 的下一版本。</span><span class="sxs-lookup"><span data-stu-id="d210c-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="d210c-126">默认情况下, 不会向 Microsoft 发送任何信息。</span><span class="sxs-lookup"><span data-stu-id="d210c-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="d210c-127">但是, 当你使用`-errorreport:queue`(默认情况下已启用) 编译应用程序时, 应用程序将收集其错误报告。</span><span class="sxs-lookup"><span data-stu-id="d210c-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="d210c-128">然后, 当计算机的管理员登录时, "错误报告系统" 会显示一个弹出窗口, 使管理员能够将自登录后发生的任何错误报告转发给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d210c-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d210c-129">此`/bugreport`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="d210c-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d210c-130">示例</span><span class="sxs-lookup"><span data-stu-id="d210c-130">Example</span></span>  
 <span data-ttu-id="d210c-131">下面的示例将`T2.vb`所有错误报告信息编译并放入文件`Problem.txt`中。</span><span class="sxs-lookup"><span data-stu-id="d210c-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d210c-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="d210c-132">See also</span></span>

- [<span data-ttu-id="d210c-133">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="d210c-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d210c-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d210c-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="d210c-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="d210c-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="d210c-136">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="d210c-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="d210c-137">[Ws-securitypolicy 的 trustLevel 元素 (ASP.NET 设置架构)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d210c-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
