---
title: C# 编译器选项
ms.date: 07/20/2015
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: a0affaf3691d2392c9f8d7502204d0122f2ea428
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="c-compiler-options"></a><span data-ttu-id="99818-102">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="99818-102">C# Compiler Options</span></span>
<span data-ttu-id="99818-103">编译器生成可执行 (.exe) 文件、动态链接库 (.dll) 或者代码模块 (.netmodule)。</span><span class="sxs-lookup"><span data-stu-id="99818-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>  
  
 <span data-ttu-id="99818-104">每个编译器选项均有两种形式：**-option** 和 **/option**。</span><span class="sxs-lookup"><span data-stu-id="99818-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="99818-105">此文档仅介绍 **-option** 形式。</span><span class="sxs-lookup"><span data-stu-id="99818-105">The documentation only shows the **-option** form.</span></span>  
  
 <span data-ttu-id="99818-106">在 Visual Studio 中，可在 Web.config 文件中设置编译器选项。</span><span class="sxs-lookup"><span data-stu-id="99818-106">In Visual Studio, you set compiler options in the web.config file.</span></span> <span data-ttu-id="99818-107">有关详细信息，请参阅 [\<compiler> 元素](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)。</span><span class="sxs-lookup"><span data-stu-id="99818-107">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99818-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="99818-108">In This Section</span></span>  
 [<span data-ttu-id="99818-109">在命令行上使用 csc.exe 生成</span><span class="sxs-lookup"><span data-stu-id="99818-109">Command-line Building With csc.exe</span></span>](command-line-building-with-csc-exe.md)  
 <span data-ttu-id="99818-110">介绍了如何通过命令行生成 Visual C# 应用程序。</span><span class="sxs-lookup"><span data-stu-id="99818-110">Information about building a Visual C# application from the command line.</span></span>  
  
 [<span data-ttu-id="99818-111">如何：为 Visual Studio 命令行设置环境变量</span><span class="sxs-lookup"><span data-stu-id="99818-111">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 <span data-ttu-id="99818-112">介绍了运行 vsvars32.bat 启用命令行生成的步骤。</span><span class="sxs-lookup"><span data-stu-id="99818-112">Provides steps for running vsvars32.bat  to enable command-line builds.</span></span>  
  
 [<span data-ttu-id="99818-113">按类别列出的 C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="99818-113">C# Compiler Options Listed by Category</span></span>](listed-by-category.md)  
 <span data-ttu-id="99818-114">分类列出了编译器选项。</span><span class="sxs-lookup"><span data-stu-id="99818-114">A categorical listing of the compiler options.</span></span>  
  
 [<span data-ttu-id="99818-115">按字母顺序列出的 C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="99818-115">C# Compiler Options Listed Alphabetically</span></span>](listed-alphabetically.md)  
 <span data-ttu-id="99818-116">按字母顺序列出了编译器选项。</span><span class="sxs-lookup"><span data-stu-id="99818-116">An alphabetical listing of the compiler options.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="99818-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="99818-117">Related Sections</span></span>  
 [<span data-ttu-id="99818-118">“项目设计器”->“生成”页</span><span class="sxs-lookup"><span data-stu-id="99818-118">Build Page, Project Designer</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)  
 <span data-ttu-id="99818-119">介绍了如何设置属性来控制项目的编译、生成和调试方式。</span><span class="sxs-lookup"><span data-stu-id="99818-119">Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="99818-120">介绍了 Visual C# 项目的自定义生成步骤。</span><span class="sxs-lookup"><span data-stu-id="99818-120">Includes information about custom build steps in Visual C# projects.</span></span>  
  
 [<span data-ttu-id="99818-121">默认和自定义生成</span><span class="sxs-lookup"><span data-stu-id="99818-121">Default and Custom Builds</span></span>](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 <span data-ttu-id="99818-122">介绍了生成类型和配置。</span><span class="sxs-lookup"><span data-stu-id="99818-122">Information on build types and configurations.</span></span>  
  
 [<span data-ttu-id="99818-123">准备和管理生成</span><span class="sxs-lookup"><span data-stu-id="99818-123">Preparing and Managing Builds</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="99818-124">介绍了 Visual Studio 开发环境中的生成过程。</span><span class="sxs-lookup"><span data-stu-id="99818-124">Procedures for building within the Visual Studio development environment.</span></span>
